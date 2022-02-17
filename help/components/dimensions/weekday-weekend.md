---
title: 平日／週末
description: ヒットが平日または週末のどちらで発生したかを指定します。
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 100%

---

# 平日／週末

「平日／週末」ディメンションは、ヒットが平日（月～金）または週末（土曜～日）のどちらで発生したかを分析するために使用します。ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/admin/general-acct-settings-admin.md)に基づいています。

## このディメンションへのデータ入力

このディメンションは、すべての実装で初期設定の状態で動作します。レポートスイートにデータが含まれる場合、このディメンションは機能します。

## ディメンション項目

このディメンションには、常に `"Weekday"` と `"Weekend"` の 2 つのディメンション項目が含まれます。`"Weekday"` ディメンション項目は月～金曜日のすべてのヒットに適用され、`"Weekend"` ディメンション項目は土曜日と日曜日のすべてのヒットに適用されます。
