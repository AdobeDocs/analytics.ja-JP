---
title: カスタムリンク
description: カスタムリンクの名前。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---


# カスタムリンク

「カスタムリンク」ディメンションは、サイトに実装されたカスタムリンクの名前をレポートします。このディメンションは、訪問者が最もクリックするリンクのタイプを理解したい場合に役立ちます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストでの `lnk_o` 値を持つ `pe` クエリ文字列も持つヒットについて、 ](/help/implement/validate/query-parameters.md)クエリ文字列 [`pev2` からデータを収集します。ヒット内で `pe` クエリ文字列の値が異なる場合、このディメンションはデータを収集しません。

AppMeasurement を使用してこのディメンションにデータを送信する場合：

* 目的の値を [`linkName`](/help/implement/vars/config-vars/linkname.md) 変数に入力します。
* [`linkType`](/help/implement/vars/config-vars/linktype.md) 変数を `"o"` に設定します。
* [`tl()`](/help/implement/vars/functions/tl-method.md) イメージリクエストを送信します。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
