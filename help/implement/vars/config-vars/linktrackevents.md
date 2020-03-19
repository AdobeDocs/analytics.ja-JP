---
title: linkTrackEvents
description: リンクトラッキングイメージリクエストに含めるイベントを決定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackEvents

一部の実装では、すべてのリンクトラッキングイメージリクエストにすべての変数を含めたくない場合があります。 変数と変数を使 [`linkTrackVars`](linktrackvars.md) 用して、 `linkTrackEvents` 呼び出しにディメンションと指標を選択的に含め [`tl()`](../functions/tl-method.md) ます。

この変数は、ページビュー呼び出し（メソッド）には使[`t()`](../functions/t-method.md) 用されません。

## Adobe Experience Platform Launchを使用したリンクトラッキングコールのイベント

「起動」は、インターフェイスで定義されたイベントを自動的に検出し、リンクトラッキングのヒットに含めます。

> [!IMPORTANT] カスタムコードエディターを使用して起動でイベントを設定する場合は、カスタムコードの使用にもイベントを含め `linkTrackEvents` る必要があります。

## AppMeasurementのs.linkTrackEventsとカスタムコードエディターの起動

変数 `s.linkTrackEvents` は、リンクトラッキングイメージリクエスト（メソッド）に含めるイベントのコンマ区切りリストを含む`tl()` 文字列です。 リンクトラッキングヒットに指標を含めるには、次の3つの条件を満たす必要があります。

* 目的のイベントを変数に設定し [`events`](../page-vars/events/events-overview.md) ます。 例：`s.events = "event1";`。
* Set the `events` variable in `linkTrackVars`. 例：`s.linkTrackVars = "events";`。
* 目的のイベントを変数に設定し `linkTrackEvents` ます。 例：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

この変数のデフォルト値は空の文字列です。 この変数を定義しない場合、すべてのイベントがリンクトラッキングイメージリクエストに含まれます。 Launchは、インターフェイスで設定されたイベントに基づいてこの変数を自動的に設定するので、常にLaunchを使用する実装で設定されます。

> [!TIP] この変数でイベントを指定する場合は、Analytics`s.`オブジェクト識別子()の使用を避けます。 例えば、は正し `s.linkTrackEvents = "event1";` いが、は正し `s.linkTrackEvents = "s.event1";` くないとします。

## 例   

次のリンクトラッキング機能は、アドビに送 `event1` 信されるイメ `event2`ージリクエストに（非）のみを含みます。

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
