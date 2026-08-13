---
title: useBeacon
description: useBeacon を使用すると、AppMeasurement で強制的にブラウザーの sendBeacon API を使用できます
feature: Appmeasurement Implementation
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/-drQZhKcoWzWfwcbFKms2xV2eunuNYIjkm4AWTmD-Pg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 60%

---

# useBeacon

最新のブラウザーのほとんどに `navigator.sendBeacon()` ネイティブメソッドが含まれています。 HTTP 経由で Web サーバーに少量のデータを非同期に送信します。 `useBeacon` 変数が有効な場合、AppMeasurement は `navigator.sendBeacon()` メソッドを使用できます。 これは、ページがアンロードされる前に情報を送信する離脱リンクなどの状況で役立ちます。

`useBeacon` が有効である場合、アドビに送信される次のヒットでは、標準の `GET` イメージリクエストの代わりに、ブラウザーの `navigator.sendBeacon()` メソッドが使用されます。 この変数は、[`s.t()`](../functions/t-method.md) と [`s.tl()`](../functions/tl-method.md) の両方のイメージリクエストに適用されます。 AppMeasurement 2.17.0 以降が必要です。

>[!TIP]
>
>AppMeasurement は、離脱リンクイメージリクエストで `useBeacon` を自動的に有効にします。

訪問者が `useBeacon` をサポートしていないブラウザーを使用している場合、`navigator.sendBeacon()` 変数は無視されます。 この変数を使用するには、AppMeasurement 2.16.0 以降が必要です。

## Web SDK拡張機能を使用したsendBeacon APIの使用

アクション設定内の&#x200B;**[!UICONTROL ドキュメントが]**&#x200B;のチェックボックスを解除し、Adobeに送信されたデータがsendBeacon APIを使用するかどうかを判断します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL &#x200B; ルール &#x200B;]」タブに移動し、目的のルールをクリックします。
1. [!UICONTROL &#x200B; アクション &#x200B;]で、目的のアクションをクリックするか、**&#39;+&#39;** アイコンをクリックして新しいアクションを追加します。
1. [!UICONTROL 拡張機能] ドロップダウンリストを&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;に、[!UICONTROL Action Type]を&#x200B;**[!UICONTROL Send event]**&#x200B;に設定します
1. 右側の「**[!UICONTROL ドキュメントがアンロードされます]**」チェックボックスをクリックします。

このチェックボックスをオンにすると、データはsendBeacon APIを使用してAdobeに送信されます。 デフォルトでは選択解除されています。

## Web SDKを手動で実装するsendBeacon APIの使用

イベントの送信時に`documentUnloading`を`true`に設定します。 設定しない場合、デフォルト値は`false`です。

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

詳しくは、Web SDK ドキュメントの「[sendBeacon APIの使用](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=ja#using-the-sendbeacon-api)」を参照してください。

## Adobe Analytics拡張機能を使用したビーコンの使用

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.useBeaconとAnalytics拡張機能のカスタムコードエディター

`s.useBeacon` 変数は、AppMeasurement がブラウザーの `navigator.sendBeacon()` メソッドを使用するかどうかを決定するブール値です。 デフォルト値は `false` です。 `navigator.sendBeacon()` の非同期性を使用する場合は、トラッキング関数を呼び出す前にこの変数を `true` に設定します。

```js
s.useBeacon = true;
```

>[!NOTE]
>
>トラッキングコールの実行後、この変数は `false` にリセットされます。 実装が同じページ読み込みで複数のイメージリクエストを送信する場合（単一ページのアプリケーションなど）、各トラッキングコールの前にこの変数を `true` に設定します。
