---
title: 平日／週末
description: ヒットが平日または週末のどちらで発生したかを指定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 68%

---


# 平日／週末

「平日／週末」ディメンションは、ヒットが平日（月～金）または週末（土曜～日）のどちらで発生したかを分析するために使用します。ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/admin/general-acct-settings-admin.md)に基づいています。

## このディメンションへのデータ入力

このディメンションは、すべての実装で初期設定の状態で動作します。レポートスイートにデータが含まれる場合、このディメンションは機能します。

## Dimension項目

This dimension always contains exactly two dimension items: `"Weekday"` and `"Weekend"`. The dimension item `"Weekday"` applies to all hits Monday through Friday, while the dimension item `"Weekend"` applies to all hits on Saturday and Sunday.
