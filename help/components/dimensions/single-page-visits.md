---
title: 直帰数（ディメンション）
description: 訪問が 1 つのページで構成されていることを示すフラグ。
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
TQID: https://experienceleague.adobe.com/mMxxlVpQi7IsSuxSZGijnvWeoqCa-ybf8otPRDf6AyQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 144
ht-degree: 91%

---

# 直帰数

*このヘルプページでは、「単一ページ訪問」が[&#x200B; ディメンション &#x200B;](overview.md)として機能する仕組みについて説明します。 詳しくは、[直帰数](../metrics/single-page-visits.md)指標を参照してください。*

「直帰数」ディメンションは、一意の[ページ](page.md)ディメンション項目 1 つで構成される訪問回数をレポートします。 これは、[直帰数](../metrics/single-page-visits.md)指標のディメンション形式です。

このディメンションは、最も一般的に、[セグメント化](../segmentation/seg-home.md)のコンポーネントとして使用されます。 通常、これは、レポートでディメンションとして使用されません。

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。 レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

唯一のディメンション項目は `"Enabled"` です。 1 回の訪問が 1 つのページで構成されている場合、ヒットはこの値に設定されます。 その他のヒットはすべてこのレポートから除外されます。
