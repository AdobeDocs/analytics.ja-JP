---
title: 直帰数（ディメンション）
description: 訪問が 1 つのページで構成されていることを示すフラグ。
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 91%

---

# 直帰数

*このヘルプページでは、「単一ページ訪問数」が [ ディメンション ](overview.md) としてどのように機能するかについて説明します。 詳しくは、[直帰数](../metrics/single-page-visits.md)指標を参照してください。*

「直帰数」ディメンションは、一意の[ページ](page.md)ディメンション項目 1 つで構成される訪問回数をレポートします。これは、[直帰数](../metrics/single-page-visits.md)指標のディメンション形式です。

このディメンションは、最も一般的に、[セグメント化](../segmentation/seg-home.md)のコンポーネントとして使用されます。通常、これは、レポートでディメンションとして使用されません。

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

唯一のディメンション項目は `"Enabled"` です。1 回の訪問が 1 つのページで構成されている場合、ヒットはこの値に設定されます。その他のヒットはすべてこのレポートから除外されます。
