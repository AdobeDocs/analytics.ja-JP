---
title: 訪問の深さ
description: 訪問の深さをレポートする訪問ベースのディメンション。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 57%

---


# 訪問の深さ

「訪問の深さ」ディメンションは、訪問中に訪問者が閲覧したページ表示の数をレポートします。Visit depth increases only if the hit is a page view, and the [Page](page.md) dimension is not the same as the last page view&#39;s dimension item. これは訪問ベースのディメンションで、訪問全体で同じ値が含まれます。この変数は、訪問が終了した後の訪問でのすべてのヒットに対して設定されます。

## このディメンションへのデータ入力

このディメンションは、すべての実装で初期設定の状態で動作します。レポートスイートにデータが含まれる場合、このディメンションは機能します。

## Dimension項目

Dimension items include the string `"Pages per visit"` followed by a number representing the number of pages in the visit. The dimension item of `"Pages per visit: 1"` represents a single-page visit, while the dimension item `"Pages per visit: 8"` represents a visit with 8 page views (and any number of link tracking calls).

## ヒットの深さとの比較

ディメンション間の比較については、「[ヒットの深さ](hit-depth.md)」を参照してください。