---
title: 出口ディメンション
description: 出口ディメンションと、その使用をリストします。
keywords: 出口ページ、出口サイトセクション、出口サーバー、出口 custom insight
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 94%

---

# 出口ディメンション

*このヘルプページでは、EXIT が [ ディメンション ](overview.md) としてどのように機能するかを説明します。 出口が指標として機能する方法について詳しくは、[出口](../metrics/exits.md)指標を参照してください。*

出口ディメンションは、最後のディメンション項目を記録し、訪問のすべてのヒットに遡って適用します。出口ディメンションは、レポートスイート設定の「[トラフィック変数](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)」でパスが有効になっているすべての変数で使用できます。

## 出口ディメンションへのデータ入力

特定の出口ディメンションは、関連付けられたトラフィック変数に基づいています。出口以外の変数にデータが含まれる場合は、関連する出口ディメンションにもデータが含まれます。トラフィック変数にデータが含まれる場合、出口ディメンションに対して実装の変更は必要ありません。

## ディメンション項目

出口変数は通常、実装内のカスタム文字列に基づくので、組織でディメンション項目を決定します。特定の出口ディメンションの項目は、関連付けられた出口以外のディメンションのディメンション項目と一致します。例えば、「出口ページ」ディメンションのディメンション項目には、「ページ」ディメンションに類似したディメンション項目が含まれています。
