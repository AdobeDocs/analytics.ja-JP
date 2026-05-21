---
title: linkTrackEvents
description: リンクトラッキングイメージリクエストに含めるイベントを決定します。
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
TQID: https://experienceleague.adobe.com/7BKaDxchTRu39doWzm8f32DOemgpvj1s-4uzfjJkOEA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 66%

---

# linkTrackEvents

一部の実装では、すべての変数をすべてのリンクトラッキングイメージリクエストに含めたくない場合があります。 [`linkTrackVars`](linktrackvars.md) 変数と `linkTrackEvents` 変数を使用して、[`tl()`](../functions/tl-method.md) の呼び出しにディメンションと指標を選択的に含めます。

この変数は、ページビュー呼び出し（[`t()`](../functions/t-method.md) メソッド）には使用されません。

## Web SDKを使用して、XDM イベントに含めるAnalytics イベントを決定します

Web SDKでは、リンクトラッキング呼び出しの特定のフィールドは除外されません。 ただし、`onBeforeEventSend` コールバックを使用して、データをAdobeに送信する前に、目的のフィールドをクリアまたは設定できます。 詳しくは、Web SDK ドキュメントの「[&#x200B; グローバルにイベントを変更する](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)」を参照してください。

## Adobe Analytics拡張機能を使用したリンクトラッキング呼び出しのイベント

カスタムコードを使用しない場合、Adobe Experience Platform では、定義済みのイベントが自動的にリンクトラッキングのヒットに含まれます。

>[!IMPORTANT]
>
>Analytics拡張機能のカスタムコードエディターでイベントを設定する場合は、カスタムコードも使用して`linkTrackEvents`にイベントを含める必要があります。

## AppMeasurementのs.linkTrackEventsとAnalytics拡張機能のカスタムコードエディター

`s.linkTrackEvents` 変数は、リンクトラッキングイメージリクエスト（`tl()` メソッド）に含めるイベントのコンマ区切りリストを含む文字列です。 リンクトラッキングヒットに指標を含めるには、次の 3 つの条件を満たす必要があります。

* 目的のイベントを [`events`](../page-vars/events/events-overview.md) 変数に設定します。 例：`s.events = "event1";`。
* `events` 変数を `linkTrackVars` に設定します。 例：`s.linkTrackVars = "events";`。
* 目的のイベントを `linkTrackEvents` 変数に設定します。 例：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

この変数のデフォルト値は空の文字列です。 この変数を定義しない場合、すべてのイベントがリンクトラッキングイメージリクエストに含まれます。 データ収集は、インターフェイスで設定されたイベントに基づいてこの変数を自動的に設定するので、Adobe Experience Platform のタグを使用する実装では常に設定されます。

>[!TIP]
>
>この変数でイベントを指定する場合は、Analytics オブジェクト識別子（`s.`）を使用しないでください。 例えば、`s.linkTrackEvents = "event1";` は正しいですが、`s.linkTrackEvents = "s.event1";` は正しくありません。

## 例

次のリンクトラッキング関数は、アドビに送信されるイメージリクエストに `event1` のみを含みます（`event2` は含みません）。

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
