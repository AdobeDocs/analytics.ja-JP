---
title: 午前／午後
description: ヒットが午前中に発生したか、午後 2 時間に発生したかを判定します。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 86%

---

# 午前／午後

「午前/午後」 [ディメンション](overview.md) ヒットが午前中に発生したか、午後 2 時間に発生したかに関するインサイトを提供します。 ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)に基づいています。

## このディメンションへのデータ入力

このディメンションは設定なしで使用できます。変更する設定はありません。レポートスイートのタイムゾーンに依存する唯一のものです。タイムゾーンによって、午前と午後のどちらの時間が決まります。

## ディメンション項目

このディメンションには、常に `"AM"` と `"PM"` の 2 つのディメンション項目が含まれます。`"AM"` ディメンション項目は、午前 12:00 ～ 11:59 のすべてのヒットに適用され、`"PM"` ディメンション項目は、午後 12:00 ～ 11:59 のすべてのヒットに適用されます。
