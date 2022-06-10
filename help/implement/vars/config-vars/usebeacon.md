---
title: useBeacon
description: useBeacon を使用すると、AppMeasurement で強制的にブラウザーの sendBeacon API を使用できます
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 54%

---

# useBeacon

最新のブラウザーのほとんどに `navigator.sendBeacon()` ネイティブメソッドが含まれています。HTTP 経由で Web サーバーに少量のデータを非同期に送信します。`useBeacon` 変数が有効な場合、AppMeasurement は `navigator.sendBeacon()` メソッドを使用できます。これは、ページがアンロードされる前に情報を送信する離脱リンクなどの状況で役立ちます。

`useBeacon` が有効である場合、アドビに送信される次のヒットでは、標準の `GET` イメージリクエストの代わりに、ブラウザーの `navigator.sendBeacon()` メソッドが使用されます。この変数は、[`s.t()`](../functions/t-method.md) と [`s.tl()`](../functions/tl-method.md) の両方のイメージリクエストに適用されます。AppMeasurement 2.17.0 以降が必要です。

>[!TIP]
>
> AppMeasurement は、離脱リンクイメージリクエストで `useBeacon` を自動的に有効にします。

訪問者が `useBeacon` をサポートしていないブラウザーを使用している場合、`navigator.sendBeacon()` 変数は無視されます。この変数を使用するには、AppMeasurement 2.16.0 以降が必要です。

## Web SDK 拡張機能を使用した sendBeacon API の使用

この **[!UICONTROL ドキュメントはアンロードされます]** 「アクション設定」内のチェックボックスは、Adobeに送信するデータが sendBeacon API を使用するかどうかを指定します。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL ルール] 」タブをクリックし、目的のルールをクリックします。
1. の下 [!UICONTROL アクション]、目的のアクションをクリックするか、 **&#39;+&#39;** アイコンをクリックして新しいアクションを追加します。
1. 「拡張機能」ドロップダウンを「 **[!UICONTROL Adobe Experience Platform Web SDK]** そして [!UICONTROL アクションタイプ] から **[!UICONTROL イベントを送信]**
1. チェックボックスをクリックします。 **[!UICONTROL ドキュメントはアンロードされます]** 右側に

このボックスをオンにすると、データが sendBeacon API を使用してAdobeに送信されます。 デフォルトでは選択解除されています。

## Web SDK を手動で実装する sendBeacon API の使用

設定 `documentUnloading` から `true` イベントを送信する際に使用します。 設定しない場合、デフォルト値はです。 `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

詳しくは、 [sendBeacon API の使用](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) （ Web SDK ドキュメント）を参照してください。

## Adobe Analytics拡張機能を使用したビーコンの使用

Adobe Analytics拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement の s.useBeacon と Analytics 拡張機能のカスタムコードエディター

`s.useBeacon` 変数は、AppMeasurement がブラウザーの `navigator.sendBeacon()` メソッドを使用するかどうかを決定するブール値です。デフォルト値は `false` です。`navigator.sendBeacon()` の非同期性を使用する場合は、トラッキング関数を呼び出す前にこの変数を `true` に設定します。

```js
s.useBeacon = true;
```

>[!NOTE]
>
> トラッキングコールの実行後、この変数は `false` にリセットされます。実装が同じページ読み込みで複数のイメージリクエストを送信する場合（単一ページのアプリケーションなど）、各トラッキングコールの前にこの変数を `true` に設定します。
