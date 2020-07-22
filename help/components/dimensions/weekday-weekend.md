---
title: 平日 / 週末
description: ヒットが平日または週末のどちらで発生したかを指定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# 平日 / 週末

「平日/週末」ディメンションは、ヒットが平日（月～金）または週末（土曜～日）のどちらで発生したかを分析するために使用します。 The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## このディメンションにデータを入力する

このディメンションは、すべての実装で初期設定の状態で動作します。 レポートスイートにデータが含まれる場合、このディメンションは機能します。

## ディメンション項目

このディメンションには、常に2つのディメンション項目が含まれます。 `"Weekday"` と `"Weekend"`。 ディメンション項目 `"Weekday"` は月曜日から金曜日のすべてのヒットに適用され、ディメンション項目は土曜日と日曜日のすべてのヒットに `"Weekend"` 適用されます。
