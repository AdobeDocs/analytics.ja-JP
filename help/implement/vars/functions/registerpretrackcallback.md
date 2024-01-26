---
title: registerPreTrackCallback
description: アドビにヒットを送信する前に実行するコールバック関数を作成します。
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 55%

---

# registerPreTrackCallback

`registerPreTrackCallback` 変数を使用すると、イメージリクエスト URL がコンパイルされたがまだ送信されていないときに実行する JavaScript 関数をフックできます。この変数を使用して、AppMeasurement によって収集されたデータをパートナーまたは社内インフラストラクチャに送信できます。

>[!WARNING]
>
>次のようなトラッキングコールを実行しない [`t()`](t-method.md) または [`tl()`](tl-method.md) 内側 `registerPreTrackCallback` 変数を使用します。 この変数でトラッキングコールを設定すると、イメージリクエストが無限ループに陥ります。

`registerPreTrackCallback` 変数を呼び出すたびに、その関数をフックして、イメージリクエスト URL がコンパイルされるたびに実行します。同じページの読み込みで同じ関数を複数回登録しないでください。

>[!NOTE]
>
> `registerPreTrackCallback` と `registerPostTrackCallback` の間に呼び出される関数のタイミングと順序は保証されません。この 2 つの関数間の依存関係を避けます。

## Web SDK 拡張機能を使用したトラック前のコールバック

Web SDK は、データがコンパイルされた後、かつデータがAdobeに送信される前に、関数をフックすることはできません。 ただし、 `onBeforeEventSend` ：データが送信される直前に実行する関数を登録します。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用する UI。
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. の下 [!UICONTROL データ収集]をクリックし、 **[!UICONTROL イベント送信コールバックコードの前に編集]** 」ボタンをクリックします。
1. エディターに目的のコードを配置します。

## Web SDK の手動実装によるトラック前のコールバック

Web SDK は、データがコンパイルされた後、かつデータがAdobeに送信される前に、関数をフックすることはできません。 ただし、 `onBeforeEventSend` を登録して、 `doPlugins`. 詳しくは、 [イベントのグローバルな変更](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) （ Web SDK ドキュメント）を参照してください。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Adobe Analytics拡張機能を使用したトラック前のコールバック

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.registerPreTrackCallback

`s.registerPreTrackCallback` は、関数を唯一の引数として受け取る関数です。ネストされた関数は、イメージリクエストの送信直前に実行されます。

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

コードでイメージリクエスト URL を使用する場合は、ネストされた関数内で `requestUrl` 文字列引数を参照します。`requestUrl` 変数は、目的の用途に合わせて解析できます。この変数を調整しても、データ収集には影響しません。

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
> ページ変数の設定やこの関数内の `requestUrl` 文字列の変更は、この関数呼び出しの直後に送信されるイメージリクエストには影響&#x200B;**しません**。代わりに、[`doPlugins()`](doplugins.md) 変数を使用します。
