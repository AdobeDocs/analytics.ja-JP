---
title: 直帰数（指標）
description: 訪問で、「ページ」ディメンション項目が変更されなかった回数。
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 34%

---

# 直帰数

*このヘルプページでは、「直帰数」が指標としてどのように機能するかを説明します。詳しくは、[直帰数](../dimensions/single-page-visits.md)ディメンションを参照してください。*

**[!UICONTROL 単一ページ訪問]**[ 指標 ](overview.md) は、「[ ページ ](../dimensions/page.md)」ディメンション項目に訪問全体で単一の値のみが含まれている訪問回数を示します。 この指標は、短い訪問を表示したいが、[[!UICONTROL バウンス]](bounces.md)ほど厳しいルールを持たないディメンションのコンテキストで役立ちます。

## この指標の計算方法

この指標の定義は、[[!UICONTROL  繰り返しインスタンスをカウント ]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) のプロジェクト設定によって異なります。

* **[!UICONTROL 繰り返しインスタンスをカウント ] 有効**:[!UICONTROL  ページ ] ディメンションにその訪問の値が 1 つ含まれている訪問の回数をカウントします。 訪問者がページをリロードすると、単一ページ訪問として不適格になります。
* **[!UICONTROL 繰り返しインスタンスをカウント ] 無効**: [!UICONTROL  ページ ] ディメンションに訪問全体で一意の値が 1 つ含まれている訪問の回数をカウントします。

「[!UICONTROL  繰り返しインスタンスをカウント ]」プロジェクト設定に関係なく、この指標は次のルールに従います。

* 訪問者がリンクトラッキングコールを実行した場合、訪問は引き続き単一ページ訪問として認定されます（[!UICONTROL  ページ ] ディメンションはすべてのリンクトラッキングコールから削除されます）。
* [!UICONTROL  ページ ] ディメンションが 2 番目の一意の値に変更されるとすぐに、その訪問は単一ページ訪問と認定されなくなります。

指標の比較については、「[単一アクセス](single-access.md)」を参照してください。
