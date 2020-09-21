---
title: 出口リンク
description: 出口リンクの名前。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '152'
ht-degree: 100%

---


# 出口リンク

「出口リンク」ディメンションは、サイトに実装された出口リンクの名前をレポートします。このディメンションは、サイト外のドメインを指すどのリンクが最も人気があるかを把握したい場合に役立ちます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストでの `lnk_e` 値を持つ `pe` クエリ文字列も持つヒットについて、 ](/help/implement/validate/query-parameters.md) クエリ文字列 [`pev2` からデータを収集します。ヒット内で `pe` クエリ文字列の値が異なる場合、このディメンションはデータを収集しません。

AppMeasurement を使用してこのディメンションにデータを送信する場合：

* 目的の値を [`linkName`](/help/implement/vars/config-vars/linkname.md) 変数に入力します。
* [`linkType`](/help/implement/vars/config-vars/linktype.md) 変数を `"e"` に設定します。
* [`tl()`](/help/implement/vars/functions/tl-method.md) イメージリクエストを送信します。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
