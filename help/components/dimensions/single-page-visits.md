---
title: 単一ページ訪問（ディメンション）
description: 訪問が単一ページで構成されていることを示すフラグ。
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
TQID: https://experienceleague.adobe.com/mMxxlVpQi7IsSuxSZGijnvWeoqCa-ybf8otPRDf6AyQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 66%
---
# 直帰数

>[!BEGINSHADEBOX]

*このヘルプページでは、「単一ページ訪問」が[ ディメンション ](overview.md)として機能する仕組みについて説明します。 詳しくは、[直帰数](../metrics/single-page-visits.md)指標を参照してください。*

>[!ENDSHADEBOX]

「直帰数」ディメンションは、一意の[ページ](page.md)ディメンション項目 1 つで構成される訪問回数をレポートします。 これは、[直帰数](../metrics/single-page-visits.md)指標のディメンション形式です。

このディメンションは、最も一般的に、[セグメント化](../segmentation/seg-home.md)のコンポーネントとして使用されます。 通常、これは、レポートでディメンションとして使用されません。

## このディメンションへのデータ入力

Adobeでは、各訪問に一意のページが含まれているかどうかを評価することで、このディメンションをサーバーサイドで計算します。 設定する変数はありません。すべての実装に対してすぐに使用できます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

唯一のディメンション項目は `"Enabled"` です。 1 回の訪問が単一ページで構成されている場合、ヒットはこの値に設定されます。 その他のヒットはすべてこのレポートから除外されます。
