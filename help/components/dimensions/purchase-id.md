---
title: 購入 ID
description: Data Warehouseで使用可能な、購入の一意のID。
feature: Dimensions
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 18%
---
# 購入 ID

「購入ID」 [&#x200B; ディメンション &#x200B;](overview.md)は、購入の一意のIDを提供します。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。

## このディメンションへのデータ入力

このディメンションは、[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)変数を使用して設定されます。 データフィードの`purchaseid`列に対応します。 詳しくは、[&#x200B; データ列リファレンス &#x200B;](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)を参照してください。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) |
| **Web SDK / XDM フィールド** | [`commerce.order.purchaseID`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **クエリパラメーター** | [`purchaseID`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<purchaseId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 20 バイト |
| **永続性** | ヒット |

## ディメンション項目

Dimensionの商品には、サイトで収集した購入IDが含まれます。
