---
title: 午前／午後
description: ヒットが午前中に発生したか、午後 2 時間に発生したかを判定します。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 64%

---

# 午前／午後

「AM/PM」 [&#x200B; ディメンション &#x200B;](overview.md) は、ヒットが午前または午後の時間に発生したかどうかをinsightします。 ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)に基づいています。

## このディメンションへのデータ入力

このディメンションは設定なしで使用できます。変更する設定はありません。レポートスイートのタイムゾーンに依存する唯一のものです。タイムゾーンによって、午前と午後のどちらの時間が決まります。

## ディメンション項目

このディメンションには、常に `"AM"` と `"PM"` の 2 つのディメンション項目が含まれます。ディメンション項目 `"AM"` は午前 12:00 から午前 11:59 までのすべてのヒットに適用され、ディメンション項目 `"PM"` は午後 12:00 から午後 11:59 までのすべてのヒットに適用されます。
