---
title: 平日／週末
description: ヒットが平日（月曜～金曜）と週末（土曜～日曜）のどちらに発生したかを判別します。
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 49%
---
# 平日／週末

&#39;Weekday/Weekend&#39; [ ディメンション ](overview.md)は、平日（月曜日～金曜日）または週末（土曜日～日曜日）にヒットが発生したかどうかをinsightに提供します。 ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)に基づいています。

## このディメンションにデータを入力

このディメンションは、各ヒットのタイムスタンプから派生します。設定する変数はありません。 その依存関係はレポートスイートのタイムゾーンのみであり、各ヒットの曜日を決定します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（ヒットタイムスタンプから派生） |
| **Web SDK / XDM フィールド** | なし（ヒットタイムスタンプから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | ヒット |

## ディメンション項目

このディメンションには、常に `"Weekday"` と `"Weekend"` の 2 つのディメンション項目が含まれます。 `"Weekday"` ディメンション項目は月～金曜日のすべてのヒットに適用され、`"Weekend"` ディメンション項目は土曜日と日曜日のすべてのヒットに適用されます。
