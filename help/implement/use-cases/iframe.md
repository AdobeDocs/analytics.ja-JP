---
title: AppMeasurementをiframeと共に使用する
description: iframe内で、iframeまたは親ページ内のAdobe Analytics変数にアクセスします。
translation-type: tm+mt
source-git-commit: 355985a6baa1a1112e75446012be72f5c0a1d0c2
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---


# AppMeasurementをiframeと共に使用する

AppMeasurement変数は、子iframeと親iframeの両方から参照できます。 AppMeasurementライブラリが存在する場所と同じ場所にすべての変数を定義する必要があります。 次の例では、iframeの内外に基本的なAppMeasurement変数およびメソッドを設定する方法を説明します。

Adobe Experience Platform Launchを使用する場合は、トラッカーオブジェクトがグローバルにアクセスできることを確認します。 起動ユーザーガイドの [Adobe Analytics拡張機能の概要](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) を参照してください。

>!![CAUTION]
親ページとiframeの両方にAppMeasurementライブラリを含めないでください。 これにより、複数のイメージリクエストを送信し、レポートを水増しし、課金対象のサーバーコールを増やすリスクが生じます。

## iframe内にあるAppMeasurementへのアクセス

AppMeasurement変数は、iframeオブジェクトを介してアクセスできます。 次の例では、2つの異なる方法でiframeオブジェクトを参照し、 [pageName](../vars/page-vars/pagename.md) を設定し [、](../vars/functions/t-method.md) t()メソッドを呼び出します。

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## iframe内からAppMeasurementにアクセス

親ページ上のAppMeasurement変数には、iframe内からアクセスできます。 次の例では、 [pageName](../vars/page-vars/pagename.md) を設定し、プ [ロパティを使用して](../vars/functions/t-method.md) t()メソッドを呼び出します [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) 。

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## リスナー `postMessage` とイベントリスナーの使用

または、 `postMessage` およびイベントリスナーを使用して変数を設定できます。 このメソッドでは、iframeに対する直接参照は必要ありません。

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## 制限事項

* 他のJavaScriptコードと同様、iframesはドメインとプロトコルが一致する場合にのみ通信できます。 これらの例は、iframeコンテンツが親とは異なるドメインに存在する場合は機能しません。
* AppMeasurementがiframe内に存在する場合、 [`referrer`](../vars/page-vars/referrer.md) 変数は実際の参照URLではなく親URLに設定されます。 この問題を解決するには、手動で `referrer` 変数を設定します。
* [Adobe Experience Cloudデバッガーは、iframe内でトリガーされるイメージ要求を認識しません](https://docs.adobe.com/content/help/ja-JP/debugger/using/experience-cloud-debugger.html) 。
* iframe内でクリックされたリンク上でヒートマップがActivity Mapに表示されない。 代わりに、iframe全体がハイライト表示されます。
