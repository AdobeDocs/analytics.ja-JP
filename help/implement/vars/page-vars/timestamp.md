---
title: タイムスタンプ
description: ヒットのタイムスタンプを手動で設定します。
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/f2r9jWtF5HgCP6jUKg3YnLFxNwx1DiUBI-2Nquy5-K0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 82%

---

# タイムスタンプ

`timestamp` 変数は、タイムスタンプが有効なレポートスイートのヒットのタイムスタンプを手動で設定します。

>[!WARNING]
>
>レポートスイートでタイムスタンプ付きのヒットを受け入れるように明示的に設定されていない場合は、この変数を使用しないでください。 AppMeasurement は、タイムスタンプ付きのヒットをサポートしないレポートスイートのヒットの時間を自動的に設定します。 この変数を含むヒットを、タイムスタンプをサポートしないレポートスイートに送信すると、そのデータは永久的に失われます。

## Web SDKを使用したタイムスタンプ

タイムスタンプは、[XDM フィールド `xdm.timestamp`の下のAdobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md)にマッピングされています。 このフィールドはUnix時間のみをサポートします。

## Adobe Analytics拡張機能を使用したタイムスタンプ

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.timestampとAnalytics拡張機能のカスタムコードエディター

`s.timestamp` 変数は、ヒットの日時を含む文字列です。 有効なタイムスタンプ形式は、[ISO 8601](https://ja.wikipedia.org/wiki/ISO_8601)と[Unix time](https://ja.wikipedia.org/wiki/UNIX時間)です（秒単位）。

```js
// Timestamp using ISO 8601
s.timestamp = "2024-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## ISO 8601 値

[ISO 8601](https://ja.wikipedia.org/wiki/ISO_8601) で表される日付と時間は、様々な形式を取ることができます。 アドビは、ISO 8601 のすべての機能をサポートしているわけではありません。

* 日付と時刻を `T` で区切り、両方を指定する必要があります。
* 時間と分が必要です。秒はオプションですが、推奨されます。
* 曜日と年間通算日はサポートされません。
* 日付は標準形式と拡張形式のどちらでも指定できます。 例えば、`2024-01-01T00:00:00Z` と `20240101T000000Z` は両方とも有効です。
* 分数の小数値と秒数は技術的に有効ですが、小数値はアドビでは無視されます。
* タイムゾーンは、標準形式と拡張形式でサポートされています。

次に、`timestamp` 変数内の有効な ISO 8601 値の例を示します。

```text
2024-01-01T00:00:00+00:00
2024-01-01T00:00:00Z
2024-01-01T00:00:00
2024-01-01T00:00
20240101T000000+0000
20240101T000000Z
20240101T000000
20240101T0000
```
