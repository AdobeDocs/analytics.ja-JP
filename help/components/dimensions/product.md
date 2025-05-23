---
title: '製品         '
description: 製品名。
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 91%

---

# 製品         

「製品 [ ディメンション ](overview.md) は、ヒット内の製品名をレポートします。 これは、`products` 変数を使用し、トップセラーや最も多く閲覧された製品に関する指標を確認したい場合に便利です。サイトに製品が存在しない場合、このディメンションは意図的に空白にする可能性があります。

## このディメンションへのデータ入力

このディメンションは、[`products`](/help/implement/vars/page-vars/products.md) 変数内の文字列の 2 番目の部分を参照します。最初と 2 番目のセミコロン（`;`）の間の文字は、このディメンションに入力されます。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。製品に対して一貫した命名規則を設定することをお勧めします。[分類](../classifications/classifications-overview.md)は、別の方法で製品をグループ化したり、わかりやすい名前を付けたりする場合に利用できます。「製品」ディメンションと「カテゴリ」ディメンションの両方を使用することをお勧めします。
