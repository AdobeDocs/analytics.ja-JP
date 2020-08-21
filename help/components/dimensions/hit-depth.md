---
title: ヒットの深さ
description: 訪問へのヒット数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 75%

---


# ヒットの深さ

「ヒットの深さ」ディメンションは、特定のヒットが訪問までどの程度あるかをレポートします。このディメンションは、訪問者がサイト上でアクションを実行する訪問までの距離を把握するのに役立ちます。ヒットの深さでは、ページビュー（[`t()`](/help/implement/vars/functions/t-method.md)）やリンクトラッキングのヒット（[`tl()`](/help/implement/vars/functions/tl-method.md)）など、すべてのタイプのヒットをカウントします。

## このディメンションへのデータ入力

このディメンションは、すべての実装で初期設定の状態で動作します。レポートスイートにデータが含まれる場合、このディメンションは機能します。

## Dimension項目

Dimension items include the string `"Hit Depth"` followed by a number representing the number of hits into the visit. The dimension item of `"Hit Depth 1"` represents the first hit of the visit, while the dimension item `"Hit Depth 8"` represents the 8th hit of the visit.

## 訪問の深さとの比較

ヒットの深さでは、ページビューやリンクトラッキングのヒットなど、すべてのタイプのヒットがカウントされます。Visit depth only increments for page view hits, _and_ the [Page](page.md) dimension item is not the same as the value on the previous page. また、訪問の深さは訪問ベースのディメンションです。つまり、訪問のすべてのヒットに対して同じ値になります。次の表に、訪問の例と、ヒットの深さと訪問の深さをどのように考慮するかを示します。

| ページシーケンス | ヒットの深さ | 訪問の深さに対するカウント？ | 訪問の深さ |
| --- | --- | --- | --- |
| ホームページ | 1 | ○ | 4 |
| 製品紹介ページ | 2 | ○ | 4 |
| ホームページ | 3 | ○ | 4 |
| カスタムリンククリック | 4 | いいえ（カスタムリンク） | 4 |
| カスタムリンククリック | 5 | いいえ（カスタムリンク） | 4 |
| 製品紹介ページ | 6 | ○ | 4 |
| カスタムリンククリック | 7 | いいえ（カスタムリンク） | 4 |
| 製品紹介ページ | 8 | いいえ（前のページと同じ） | 4 |
