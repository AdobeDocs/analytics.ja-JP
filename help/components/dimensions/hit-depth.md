---
title: ヒットの深さ
description: 訪問へのヒット数。
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 94%

---

# ヒットの深さ

「ヒットの深さ」 [ ディメンション ](overview.md) は、特定のヒットが訪問のどこまで到達したかをレポートします。 このディメンションは、訪問者がサイト上でアクションを実行する訪問までの距離を把握するのに役立ちます。ヒットの深さでは、ページビュー（[`t()`](/help/implement/vars/functions/t-method.md)）やリンクトラッキングのヒット（[`tl()`](/help/implement/vars/functions/tl-method.md)）など、すべてのタイプのヒットをカウントします。

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

ディメンション項目には、`"Hit Depth"` 文字列の後に、訪問へのヒット数を表す数値が続きます。`"Hit Depth 1"` ディメンション項目は訪問の最初のヒットを表し、`"Hit Depth 8"` ディメンション項目は訪問の 8 番目のヒットを表します。

## 訪問の深さとの比較

ヒットの深さでは、ページビューやリンクトラッキングのヒットなど、すべてのタイプのヒットがカウントされます。訪問の深さは、ページビューのヒットに対してのみ増加します。_そして_、[ページ](page.md)ディメンションの項目が前のページの値と同じではありません。また、訪問の深さは訪問ベースのディメンションです。つまり、訪問のすべてのヒットに対して同じ値になります。次の表に、訪問の例と、ヒットの深さと訪問の深さをどのように考慮するかを示します。

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
