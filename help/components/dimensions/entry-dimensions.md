---
title: 入口ディメンション
description: 入口ディメンションとその使用をリストします。
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 58%

---


# 入口ディメンション

*このヘルプページでは、入口がディメンションとして機能するしくみについて説明します。入口が指標として機能する方法について詳しくは、[入口](../metrics/entries.md)指標を参照してください。*

入口ディメンションは訪問ベースです。これらのディメンションは、最初のディメンション項目を記録し、その訪問の全期間保持します。 入口ディメンションは、レポートスイート設定の「[トラフィック変数](/help/admin/admin/c-traffic-variables/traffic-var.md)」でパスが有効になっているすべての変数で使用できます。

## 入口ディメンションへのデータ入力

指定された入口ディメンションは、関連付けられたトラフィック変数に基づいています。入口変数以外の変数にデータが含まれている場合は、関連する入口ディメンションにもデータが含まれます。トラフィック変数にデータが含まれる場合、入口ディメンションに対して実装の変更は必要ありません。

## Dimension項目

エントリ変数は通常、実装内のカスタム文字列に基づいているので、組織でディメンション項目が何であるかが決定されます。 指定されたエントリディメンションの値は、関連付けられた非エントリディメンションのディメンション項目と一致します。 例えば、「入口ページ」ディメンションのディメンション項目には、「ページ」ディメンションに同様のディメンション項目が含まれています。

## オリジナルの入口ページ

「オリジナルの入口ページ」ディメンションの動作は、他の入口ディメンションとは異なります。特定の訪問に関する入口ページを保持する代わりに、その訪問者の cookie が保持されるまで、最初の入口ページが保持されます。For example, if you land on `https://example.com/page4` for your first visit to the site, then a year later land on `https://example.com/store`, The &#39;Entry page original&#39; dimension lists `https://example.com/page4` as the dimension item.
