---
title: iFrames での AppMeasurement の使用
description: iframe 内で、iframe または親ページ内の Adobe Analytics 変数にアクセスします。
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
source-git-commit: 40bf2bbb522a94a678d0da1a645d83a5121c93d0
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 100%

---

# iFrames での AppMeasurement の使用

AppMeasurement 変数は、子 iframe と親 iframe の両方から参照できます。 AppMeasurement ライブラリが存在する場所と同じ場所にすべての変数を定義する必要があります。 次の例では、iframe の内外に基本的な AppMeasurement 変数およびメソッドを設定する方法を説明します。

Adobe Experience Platform Launch を使用する場合は、トラッカーオブジェクトがグローバルにアクセスできることを確認します。 Launch ユーザガイドの[Adobe Analytics 拡張機能の概要](https://docs.adobe.com/content/help/ja-JP/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html)を参照してください。

>[!CAUTION]
>
>親ページと iframe の両方に AppMeasurement ライブラリを含めないでください。 これをおこなうと、複数の画像リクエストが送信される、レポートが水増しされる、課金対象のサーバー呼び出しが増加するなどのリスクが生じます。

## iframe 内にある AppMeasurement へのアクセス

iframe オブジェクトを介して AppMeasurement 変数にアクセスできます。 これらの例では、[pageName](../vars/page-vars/pagename.md) を設定し、2 つの異なる方法を使用して [t() メソッド](../vars/functions/t-method.md)を呼び出して iframe オブジェクトを参照します。

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## iframe 内から AppMeasurement にアクセスする

iframe 内から親ページの AppMeasurement 変数にアクセスできます。 次の使用例は、[pageName](../vars/page-vars/pagename.md) を設定し、[`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp)プロパティを使用して [t()メソッド](../vars/functions/t-method.md)を呼び出しています。

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## `postMessage` とイベントリスナーを使用する

または、`postMessage` とイベントリスナーを使用して変数を設定できます。 このメソッドでは、iframe に対する直接参照は必要ありません。

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

* 他の JavaScript コードと同様、iFrames はドメインとプロトコルが一致する場合にのみ通信できます。 これらの例は、iframe コンテンツが親とは異なるドメインに存在する場合は機能しません。
* AppMeasurement が iframe 内に存在する場合、[`referrer`](../vars/page-vars/referrer.md) 変数は、実際の参照 URL ではなく親 URL に設定されます。 `referrer` 変数を手動で設定すると、この問題を解決できます。
* [Adobe Experience Cloud Debugger ](https://docs.adobe.com/content/help/ja-JP/debugger/using/experience-cloud-debugger.html)は、iframe 内でトリガーされた画像リクエストを認識しません。
* Activity Map には、iframe 内でクリックされたリンクのヒートマップは表示されません。 代わりに、iframe 全体がハイライト表示されます。
