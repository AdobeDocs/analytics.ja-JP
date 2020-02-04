---
title: linkTrackEvents
description: リンクトラッキングイメージリクエストに含めるイベントを決定します。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackEvents

一部の実装では、すべてのリンクトラッキングイメージリクエストにすべての変数を含めないでください。 変数と変数を使 `linkTrackVars` 用して、呼び `linkTrackEvents` 出しにディメンションと指標を選択的に含め `tl()` ます。

この変数は、ページビュー呼び出し(関数`t()` )には使用されません。

## Adobe Experience Platform Launchを使用したリンクトラッキングコールのイベント

「起動」は、インターフェイスで定義されたイベントを自動的に検出し、リンクトラッキングのヒットに含めます。

> [!IMPORTANT] カスタムコードエディターを使用して起動でイベントを設定する場合は、カスタムコードを使用する際にもイベントを含め `linkTrackEvents` る必要があります。

## AppMeasurementおよび起動カスタムコードエディターのs.linkTrackEvents

変数 `s.linkTrackEvents` は、リンクトラッキングイメージリクエスト（関数）に含めるイベントのコンマ区切りリストを含む文字`tl()` 列です。 リンクトラッキングヒットに指標を含めるには、次の3つの条件を満たす必要があります。

* 目的のイベントを変数に設定し `events` ます。 例：`s.events = "event1";`。
* Set the `events` variable in `linkTrackVars`. 例：`s.linkTrackVars = "events";`。
* 目的のイベントを変数に設定し `linkTrackEvents` ます。 例：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

この変数のデフォルト値は空の文字列です。 この変数を定義しない場合、すべてのイベントがリンクトラッキングイメージリクエストに含まれます。 Launchは、インターフェイスで設定されたイベントに基づいてこの変数を自動的に設定するので、常にLaunchを使用した実装で設定されます。

> [!TIP] この変数でイベントを指定する場合は、Analyticsオブジェク`s.`ト識別子()を使用しないでください。 例えば、は正し `s.linkTrackEvents = "event1";` いが、は正し `s.linkTrackEvents = "s.event1";` くない。

## 例

次のリンクトラッキング関数は、アドビに送信 `event1` されるイメ `event2`ージリクエストに（非）のみを含みます。

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
