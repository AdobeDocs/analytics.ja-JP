---
title: 午前／午後
description: ヒットが午前中に発生したか、午後 2 時間に発生したかを判定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 70%

---


# 午前／午後

「AM／PM」ディメンションは、ヒットが午前または午後の時間に発生したかどうかに関する洞察を提供します。ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/admin/general-acct-settings-admin.md)に基づいています。

## このディメンションへのデータ入力

このディメンションは設定なしで使用できます。変更する設定はありません。レポートスイートのタイムゾーンに依存する唯一のものです。タイムゾーンによって、午前と午後のどちらの時間が決まります。

## Dimension項目

This dimension always contains exactly two dimension items: `"AM"` and `"PM"`. The dimension item `"AM"` applies to all hits from 12:00 AM to 11:59 AM, while the dimension item `"PM"` applies to all hits from 12:00 PM to 11:59 PM.
