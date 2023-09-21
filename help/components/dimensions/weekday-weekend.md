---
title: 平日／週末
description: ヒットが平日または週末のどちらで発生したかを指定します。
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# 平日／週末

「平日/週末」 [ディメンション](overview.md) ヒットが平日（月～金）または週末（土～日）のどちらで発生したかを把握できます。 ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)に基づいています。

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

このディメンションには、常に `"Weekday"` と `"Weekend"` の 2 つのディメンション項目が含まれます。`"Weekday"` ディメンション項目は月～金曜日のすべてのヒットに適用され、`"Weekend"` ディメンション項目は土曜日と日曜日のすべてのヒットに適用されます。
