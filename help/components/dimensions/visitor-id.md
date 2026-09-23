---
title: 訪問者 ID
description: Data Warehouseで使用できる訪問者の一意のID。
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
source-wordcount: '133'
ht-degree: 18%
---
# 訪問者 ID

「訪問者ID」 [&#x200B; ディメンション &#x200B;](overview.md)は、各訪問者に一意のIDを提供します。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。

## このディメンションへのデータ入力

Adobeは、各訪問者の訪問者IDを自動的に生成します。 この値は、データフィードの`visid_high`列と`visid_low`列の連結値と同じです。 自動生成された値を`visitorID`変数で上書きできます。 詳しくは、[&#x200B; データ列リファレンス &#x200B;](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)を参照してください。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| **Web SDK / XDM フィールド** | なし |
| **クエリパラメーター** | [`vid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<visitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 255 バイト |
| **永続性** | 該当なし |

## ディメンション項目

Dimensionの項目には、各訪問者の一意のIDが含まれます。
