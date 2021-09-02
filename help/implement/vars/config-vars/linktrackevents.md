---
title: linkTrackEvents
description: リンクトラッキングイメージリクエストに含めるイベントを決定します。
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: ht
source-wordcount: '258'
ht-degree: 100%

---

# linkTrackEvents

一部の実装では、すべての変数をすべてのリンクトラッキングイメージリクエストに含めたくない場合があります。[`linkTrackVars`](linktrackvars.md) 変数と `linkTrackEvents` 変数を使用して、[`tl()`](../functions/tl-method.md) の呼び出しにディメンションと指標を選択的に含めます。

この変数は、ページビュー呼び出し（[`t()`](../functions/t-method.md) メソッド）には使用されません。

## Adobe Experience Platform のタグを使用したリンクトラッキング呼び出しのイベント

カスタムコードを使用しない場合、Adobe Experience Platform では、定義済みのイベントが自動的にリンクトラッキングのヒットに含まれます。

>[!IMPORTANT]
>
> カスタムコードエディターを使用してデータ収集 UI でイベントを設定する場合は、カスタムコードを使用して `linkTrackEvents` でもイベントを含める必要があります。

## AppMeasurement および カスタムコードエディターの s.linkTrackEvents

`s.linkTrackEvents` 変数は、リンクトラッキングイメージリクエスト（`tl()` メソッド）に含めるイベントのコンマ区切りリストを含む文字列です。リンクトラッキングヒットに指標を含めるには、次の 3 つの条件を満たす必要があります。

* 目的のイベントを [`events`](../page-vars/events/events-overview.md) 変数に設定します。例：`s.events = "event1";`。
* `events` 変数を `linkTrackVars` に設定します。例：`s.linkTrackVars = "events";`。
* 目的のイベントを `linkTrackEvents` 変数に設定します。例：`s.linkTrackEvents = "event1";`。

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

この変数のデフォルト値は空の文字列です。この変数を定義しない場合、すべてのイベントがリンクトラッキングイメージリクエストに含まれます。データ収集は、インターフェイスで設定されたイベントに基づいてこの変数を自動的に設定するので、Adobe Experience Platform のタグを使用する実装では常に設定されます。

>[!TIP]
>
> この変数でイベントを指定する場合は、Analytics オブジェクト識別子（`s.`）を使用しないでください。例えば、`s.linkTrackEvents = "event1";` は正しいですが、`s.linkTrackEvents = "s.event1";` は正しくありません。

## 例

次のリンクトラッキング関数は、アドビに送信されるイメージリクエストに `event1` のみを含みます（`event2` は含みません）。

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
