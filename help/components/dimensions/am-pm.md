---
title: 午前 / 午後
description: ヒットが午前中に発生したか、午後2時間に発生したかを判定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---


# 午前 / 午後

「AM/PM」ディメンションは、ヒットが午前または午後の時間に発生したかどうかに関する洞察を提供します。 The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## このディメンションにデータを入力する

この寸法は設定なしで使用できます。 変更する設定はありません。 レポートスイートのタイムゾーンに依存する唯一のものです。タイムゾーンによって、午前と午後のどちらの時間が決まります。

## ディメンション項目

このディメンションには、常に2つのディメンション項目が含まれます。 `"AM"` と `"PM"`。 ディメンション項目は午前12:00 ～ 11:59 AMのすべてのヒットに適用され、ディメンション項目は午後12:00 ～ 11:59 PMのすべてのヒット `"AM"``"PM"` に適用されます。
