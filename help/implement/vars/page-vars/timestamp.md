---
title: timestamp
description: ヒットのタイムスタンプを手動で設定します。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# timestamp

この変 `timestamp` 数は、タイムスタンプが有効なレポートスイートのヒットのタイムスタンプを手動で設定します。

> [!WARNING] レポートスイートでタイムスタンプ付きのヒットを受け入れるように明示的に設定されていない場合は、この変数を使用しないでください。 AppMeasurementは、タイムスタンプ付きのヒットをサポートしないレポートスイートのヒットの時間を自動的に設定します。 この変数を含むヒットを、タイムスタンプをサポートしないレポートスイートに送信すると、そのデータは永久的に失われます。

## Adobe Experience Platform Launchのタイムスタンプ

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.timestampとカスタムコードエディターの起動

変数 `s.timestamp` は、ヒットの日時を含む文字列です。 有効なタイムスタンプ形式 [は、](https://en.wikipedia.org/wiki/ISO_8601) ISO 8601 [、](https://en.wikipedia.org/wiki/Unix_time)Unix時間です。

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## ISO 8601値

[ISO 8601で表される日付と時間は](https://en.wikipedia.org/wiki/ISO_8601) 、様々な形式をとることができます。 アドビは、ISO 8601のすべての機能をサポートしているわけではありません。

* Both the date and time must be provided, separated by `T`.
* 時間と分が必要です。秒はオプションですが、推奨されます。
* 曜日と年間通算日はサポートされません。
* 日付は標準形式と拡張形式のどちらでも指定できます。 例えば、とは `2020-01-01T00:00:00Z` 両方と `20200101T000000Z` も有効です。
* 分数の分数と秒数は技術的に有効ですが、分数はアドビでは無視されます。
* タイムゾーンは、標準形式と拡張形式でサポートされています。

次に、変数内の有効なISO 8601値の例を示し `timestamp` ます。

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```
