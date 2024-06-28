---
title: ページビュー数
description: Adobe Analytics でディメンション項目が設定または保持された回数。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 46%

---

# ページビュー数

この **[!UICONTROL ページビュー]** [指標](overview.md) 特定のディメンション項目がページに設定または持続された回数を表示します。 これは、レポートで最も一般的で基本的な指標の 1 つです。

## この指標の計算方法

この指標は、レポートスイート内のすべてのページビュートラッキングコール（[`t()`](/help/implement/vars/functions/t-method.md)）をカウントします。ディメンションの場合、ディメンション項目が設定または持続されるヒットが含まれます。 リンクトラッキングコールは含まれません（[`tl()`](/help/implement/vars/functions/tl-method.md)）またはデータ [データソース](/help/import/data-sources/overview.md).

## 類似の指標と比較

* **ページビューと [訪問回数](visits.md)**：ページビュー数は、ページの表示回数をカウントします。 訪問回数は、訪問者のセッション数をカウントします。1 回の訪問は、1 つ以上のページビューで構成されます。
* **ページビューと [ページイベント](page-events.md)**：ページビュー数は、ページビュートラッキングコールの数をカウントします（`t()`）、リンクトラッキングコールを除外（`tl()`）に設定します。 ページイベント数は逆で、リンクトラッキングコール数をカウントし、ページビュートラッキングコール数を除外します。
