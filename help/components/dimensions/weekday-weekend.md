---
title: 平日 / 週末
description: ヒットが平日または週末のどちらで発生したかを指定します。
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# 平日 / 週末

「平日/週末」ディメンションは、ヒットが平日（月～金）または週末（土曜～日）のどちらで発生したかを分析するために使用します。 The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## このディメンションにデータを入力する

このディメンションは、すべての実装で初期設定の状態で動作します。 レポートスイートにデータが含まれる場合、このディメンションは機能します。

## 分析コード値

このディメンションには、常に2つのディメンション値が含まれます。 `"Weekday"` と `"Weekend"`。 ディメンション値は月～金曜日のすべてのヒットに `"Weekday"` 適用され、ディメンション値は土曜日と日曜日のすべてのヒット `"Weekend"` に適用されます。
