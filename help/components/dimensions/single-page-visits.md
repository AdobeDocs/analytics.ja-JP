---
title: 単一ページ訪問
description: 訪問が 1 つのページで構成されていることを示すフラグ。
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 81%

---


# 単一ページ訪問

*このヘルプページでは、「単一ページ訪問」がディメンションとして機能する方法を説明します。詳しくは、[単一ページ訪問](../metrics/single-page-visits.md)指標を参照してください。*

The &#39;Single page visits&#39; dimension reports the number of visits that consisted of a single unique [Page](page.md) dimension item. これは、[単一ページ訪問](../metrics/single-page-visits.md)指標のディメンション形式です。

このディメンションは、最も一般的に、[セグメント化](../segmentation/seg-home.md)のコンポーネントとして使用されます。通常、これは、レポートでディメンションとして使用されません。

## このディメンションへのデータ入力

このディメンションは、すべての実装で初期設定の状態で動作します。レポートスイートにデータが含まれる場合、このディメンションは機能します。

## Dimension項目

The only dimension item is `"Enabled"`. 1 回の訪問が 1 つのページで構成されている場合、ヒットはこの値に設定されます。その他のヒットはすべてこのレポートから除外されます。
