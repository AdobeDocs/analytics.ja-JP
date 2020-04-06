---
title: linkTrackEvents
description: リンクトラッキングイメージリクエストに含めるイベントを決定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkTrackEvents

一部の実装では、すべての変数をすべてのリンクトラッキングイメージリクエストに含めたくない場合があります。[`linkTrackVars`](linktrackvars.md) 変数と `linkTrackEvents` 変数を使用して、[`tl()`](../functions/tl-method.md) の呼び出しにディメンションと指標を選択的に含めます。

This variable is not used for page view calls ([`t()`](../functions/t-method.md) method).

## Adobe Experience Platform Launch を使用したリンクトラッキングコールのイベント

Launch は、インターフェイスで定義されたイベントを自動的に検出し、リンクトラッキングのヒットに含めます。

>[!IMPORTANT] カスタムコードエディターを使用して Launch でイベントを設定する場合は、カスタムコードを使用して `linkTrackEvents` でもイベントを含める必要があります。

## AppMeasurement および Launch カスタムコードエディターの s.linkTrackEvents

The `s.linkTrackEvents` variable is a string containing a comma-delimited list of events that you want to include in link tracking image requests (`tl()` method). リンクトラッキングヒットに指標を含めるには、次の 3 つの条件を満たす必要があります。

* 目的のイベントを [`events`](../page-vars/events/events-overview.md) 変数に設定します。例：`s.events = "event1";`。
* `events` 変数を `linkTrackVars` に設定します。例：`s.linkTrackVars = "events";`。
* 目的のイベントを `linkTrackEvents` 変数に設定します。例：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

この変数のデフォルト値は空の文字列です。この変数を定義しない場合、すべてのイベントがリンクトラッキングイメージリクエストに含まれます。この変数は Launch ではインターフェイスで設定されたイベントに基づいて自動的に設定されるので、Launch を使用した実装では常に設定されます。

>[!TIP] この変数でイベントを指定する場合は、Analytics オブジェクト識別子（`s.`）を使用しないでください。例えば、`s.linkTrackEvents = "event1";` は正しいですが、`s.linkTrackEvents = "s.event1";` は正しくありません。

## 例

次のリンクトラッキング関数は、アドビに送信されるイメージリクエストに `event1` のみを含みます（`event2` は含みません）。

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
