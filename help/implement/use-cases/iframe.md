---
title: AppMeasurementをiframeと共に使用する
description: iframe内で、iframeまたは親ページ内のAdobe Analytics変数にアクセスします。
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
translation-type: tm+mt
source-git-commit: 40bf2bbb522a94a678d0da1a645d83a5121c93d0
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---

# AppMeasurementをiframeと共に使用する

AppMeasurement変数は、子iframeと親iframeの両方から参照できます。 AppMeasurementライブラリが存在する場所と同じ場所にすべての変数を定義する必要があります。 次の例では、iframeの内外に基本的なAppMeasurement変数およびメソッドを設定する方法を説明します。

Adobe Experience Platform Launchを使用する場合は、トラッカーオブジェクトがグローバルにアクセスできることを確認します。 Launchユーザーガイドの[Adobe Analytics拡張機能の概要](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html)を参照してください。

>[!CAUTION]
>
>親ページとiframeの両方にAppMeasurementライブラリを含めないでください。 これにより、複数のイメージリクエストを送信し、レポートを水増しし、課金対象のサーバーコールを増やすリスクが生じます。

## iframe内にあるAppMeasurementへのアクセス

AppMeasurement変数は、iframeオブジェクトを介してアクセスできます。 次の例では、iframeオブジェクトを参照する2つの異なる方法を使用して、[pageName](../vars/page-vars/pagename.md)を設定し、[t()メソッド](../vars/functions/t-method.md)を呼び出します。

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## iframe内からAppMeasurementにアクセス

親ページ上のAppMeasurement変数には、iframe内からアクセスできます。 次の使用例は、[pageName](../vars/page-vars/pagename.md)を設定し、[`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp)プロパティを使用して[t()メソッド](../vars/functions/t-method.md)を呼び出します。

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## `postMessage`とイベントリスナーを使用

または、`postMessage`とイベントリスナーを使用して変数を設定できます。 このメソッドでは、iframeに対する直接参照は必要ありません。

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
* AppMeasurementがiframe内に存在する場合、[`referrer`](../vars/page-vars/referrer.md)変数は、実際の参照URLではなく親URLに設定されます。 `referrer`変数を手動で設定すると、この問題を解決できます。
* [Adobe Experience Cloudデバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)は、iframe内でトリガーされるイメージ要求を認識しません。
* iframe内でクリックされたリンク上でヒートマップがActivity Mapに表示されない。 代わりに、iframe全体がハイライト表示されます。
