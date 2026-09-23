---
title: Experience Cloud 訪問者 ID
description: Data Warehouseで使用可能な、訪問者のExperience Cloud ID （ECID）。
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
source-wordcount: '164'
ht-degree: 18%
---
# Experience Cloud 訪問者 ID

「Experience Cloud訪問者ID」 [ ディメンション ](overview.md)は、各訪問者のECIDを提供します。 これは、連結された2つの64 ビット番号を19桁にパディングした128 ビット番号です。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。

## このディメンションへのデータ入力

このディメンションには、訪問者ID サービス（VisitorAPI）またはExperience Platform ID サービスを使用する実装が必要です。 データフィードの`mcvisid`列に対応します。 詳しくは、[ データ列リファレンス ](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)を参照してください。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Experience Cloud訪問者ID サービスで設定） |
| **Web SDK / XDM フィールド** | なし（Experience Cloud Identity Serviceで設定） |
| **クエリパラメーター** | [`mid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<marketingCloudVisitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

Dimensionの項目には、各訪問者のExperience Cloud IDが含まれます。
