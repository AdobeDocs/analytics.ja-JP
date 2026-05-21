---
title: 午前／午後
description: ヒットが午前中に発生したか、午後 2 時間に発生したかを判定します。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 121
ht-degree: 64%

---

# 午前／午後

&#39;AM/PM&#39; [&#x200B; ディメンション &#x200B;](overview.md)は、午前または午後の時間中にヒットが発生したかどうかをinsightに提供します。 ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)に基づいています。

## このディメンションへのデータ入力

このディメンションは設定なしで使用できます。 変更する設定はありません。 レポートスイートのタイムゾーンに依存する唯一のものです。タイムゾーンによって、午前と午後のどちらの時間が決まります。

## ディメンション項目

このディメンションには、常に `"AM"` と `"PM"` の 2 つのディメンション項目が含まれます。 ディメンション項目`"AM"`は、午前12:00時から午前11:59時までのすべてのヒットに適用されます。一方、ディメンション項目`"PM"`は、午後12:00時から午後11:59時までのすべてのヒットに適用されます。
