---
title: 午前／午後
description: ヒットが午前の時間帯に発生したか、午後の時間帯に発生したかを判定します。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 33%
---
# 午前／午後

&#39;AM/PM&#39; [ ディメンション ](overview.md)は、午前または午後の時間中にヒットが発生したかどうかをinsightに提供します。 ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)に基づいています。

## このディメンションにデータを入力

このディメンションは、各ヒットのタイムスタンプから派生します。設定する変数はありません。 その唯一の依存関係は、レポートスイートのタイムゾーンで、どの時間がAMで、どの時間がPMであるかを決定します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（ヒットタイムスタンプから派生） |
| **Web SDK / XDM フィールド** | なし（ヒットタイムスタンプから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | ヒット |

## ディメンション項目

このディメンションには、常に `"AM"` と `"PM"` の 2 つのディメンション項目が含まれます。 ディメンション項目`"AM"`は午前12時00分から午前11時59分までのすべてのヒットに適用され、ディメンション項目`"PM"`は午後12時00分から午後11時59分までのすべてのヒットに適用されます。
