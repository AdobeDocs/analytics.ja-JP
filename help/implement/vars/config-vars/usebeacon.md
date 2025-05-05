---
title: useBeacon
description: useBeacon を使用すると、AppMeasurement で強制的にブラウザーの sendBeacon API を使用できます
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 62%

---

# useBeacon

最新のブラウザーのほとんどに `navigator.sendBeacon()` ネイティブメソッドが含まれています。HTTP 経由で Web サーバーに少量のデータを非同期に送信します。`useBeacon` 変数が有効な場合、AppMeasurement は `navigator.sendBeacon()` メソッドを使用できます。これは、ページがアンロードされる前に情報を送信する離脱リンクなどの状況で役立ちます。

`useBeacon` が有効である場合、アドビに送信される次のヒットでは、標準の `GET` イメージリクエストの代わりに、ブラウザーの `navigator.sendBeacon()` メソッドが使用されます。この変数は、[`s.t()`](../functions/t-method.md) と [`s.tl()`](../functions/tl-method.md) の両方のイメージリクエストに適用されます。AppMeasurement 2.17.0 以降が必要です。

>[!TIP]
>
> AppMeasurement は、離脱リンクイメージリクエストで `useBeacon` を自動的に有効にします。

訪問者が `useBeacon` をサポートしていないブラウザーを使用している場合、`navigator.sendBeacon()` 変数は無視されます。この変数を使用するには、AppMeasurement 2.16.0 以降が必要です。

## Web SDK 拡張機能を使用した sendBeacon API の使用

Action Configuration 内の **[!UICONTROL Document will unload]** チェックボックスにより、Adobeに送信されたデータが sendBeacon API を使用しているかどうかが決まります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL &#x200B; ルール &#x200B;]」タブに移動し、目的のルールをクリックします。
1. [!UICONTROL &#x200B; アクション &#x200B;] で、目的のアクションをクリックするか、「**+」** イコンをクリックして新しいアクションを追加します。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストを **[!UICONTROL Adobe Experience Platform Web SDK]** に設定し、「[!UICONTROL &#x200B; アクションタイプ &#x200B;] を **[!UICONTROL イベントを送信]** に設定します
1. 右側のチェックボックス **[!UICONTROL ドキュメントをアンロードします]** をクリックします。

このチェックボックスをオンにすると、データは sendBeacon API を使用してAdobeに送信されます。 デフォルトでは選択解除されています。

## Web SDK を手動で実装する sendBeacon API の使用

イベントを送信する際に、`documentUnloading` を `true` に設定します。 設定されていない場合、デフォルト値は `false` です。

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

詳しくは、Web SDK ドキュメントの [sendBeacon API の使用 ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) を参照してください。

## Adobe Analytics拡張機能を使用したビーコンの使用

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの s.useBeacon と Analytics 拡張機能のカスタムコードエディター

`s.useBeacon` 変数は、AppMeasurement がブラウザーの `navigator.sendBeacon()` メソッドを使用するかどうかを決定するブール値です。デフォルト値は `false` です。`navigator.sendBeacon()` の非同期性を使用する場合は、トラッキング関数を呼び出す前にこの変数を `true` に設定します。

```js
s.useBeacon = true;
```

>[!NOTE]
>
> トラッキングコールの実行後、この変数は `false` にリセットされます。実装が同じページ読み込みで複数のイメージリクエストを送信する場合（単一ページのアプリケーションなど）、各トラッキングコールの前にこの変数を `true` に設定します。
