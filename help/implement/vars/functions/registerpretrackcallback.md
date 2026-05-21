---
title: registerPreTrackCallback
description: アドビにヒットを送信する前に実行するコールバック関数を作成します。
feature: Appmeasurement Implementation
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
role: Admin, Developer
TQID: https://experienceleague.adobe.com/jL-4dheXUBOdrkCxVfq3CpWrTOgwjvEDWZ-Eg-sL2y0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 54%

---

# registerPreTrackCallback

`registerPreTrackCallback` 変数を使用すると、イメージリクエスト URL がコンパイルされたがまだ送信されていないときに実行する JavaScript 関数をフックできます。 この変数を使用して、AppMeasurement によって収集されたデータをパートナーまたは社内インフラストラクチャに送信できます。

>[!WARNING]
>
>[`t()`](t-method.md)または[`tl()`](tl-method.md)のようなトラッキング呼び出しを`registerPreTrackCallback`変数内で行わないでください。 この変数でトラッキング呼び出しを設定すると、イメージリクエストの無限ループが発生します。

`registerPreTrackCallback` 変数を呼び出すたびに、その関数をフックして、イメージリクエスト URL がコンパイルされるたびに実行します。 同じページの読み込みで同じ関数を複数回登録しないでください。

>[!NOTE]
>
>`registerPreTrackCallback` と `registerPostTrackCallback` の間に呼び出される関数のタイミングと順序は保証されません。 この 2 つの関数間の依存関係を避けます。

## Web SDK拡張機能を使用したプリトラックコールバック

Web SDKでは、データがコンパイルされた後、Adobeに送信される前に、関数をフックすることはできません。 ただし、`onBeforeEventSend`を使用して、データが送信される直前に実行する関数を登録できます。

1. Adobe IDの資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) UIにログインします。
1. 目的のタグプロパティをクリックします。
1. [!UICONTROL 拡張機能] タブに移動し、[!UICONTROL Adobe Experience Platform Web SDK]の下にある&#x200B;**[!UICONTROL Configure]** ボタンをクリックします。
1. [!UICONTROL  データ収集]で、「**[!UICONTROL イベント送信前に編集」コールバックコード]** ボタンをクリックします。
1. エディターに目的のコードを配置します。

## Web SDKを手動で実装するコールバックの事前追跡

Web SDKでは、データがコンパイルされた後、Adobeに送信される前に、関数をフックすることはできません。 ただし、`doPlugins`と同様に、`onBeforeEventSend`を使用して、データが送信される直前に実行する関数を登録できます。 詳しくは、Web SDK ドキュメントの「[ グローバルにイベントを変更する](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)」を参照してください。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Adobe Analytics拡張機能を使用したプリトラックコールバック

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.registerPreTrackCallbackとAnalytics拡張機能のカスタムコードエディター

`s.registerPreTrackCallback` は、関数を唯一の引数として受け取る関数です。 ネストされた関数は、イメージリクエストの送信直前に実行されます。

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

コードでイメージリクエスト URL を使用する場合は、ネストされた関数内で `requestUrl` 文字列引数を参照します。 `requestUrl` 変数は、目的の用途に合わせて解析できます。この変数を調整しても、データ収集には影響しません。

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

`s.registerPreTrackCallback` 関数には、ネストされた関数で使用できる、追加の引数を含めることができます。

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>ページ変数の設定やこの関数内の `requestUrl` 文字列の変更は、この関数呼び出しの直後に送信されるイメージリクエストには影響&#x200B;**しません**。 代わりに、[`doPlugins()`](doplugins.md) 変数を使用します。
