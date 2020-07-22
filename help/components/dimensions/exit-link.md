---
title: 離脱リンク
description: 離脱リンクの名前。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 0%

---


# 離脱リンク

「離脱リンク」ディメンションは、サイトに実装された離脱リンクの名前をレポートします。 このディメンションは、サイト外のドメインを指すリンクが最も人気があるかを把握したい場合に役立ちます。

## このディメンションにデータを入力する

このディメンションは、の値を持つ [`pev2` クエリ文字列も持つヒットについて、クエリリクエストの](/help/implement/validate/query-parameters.md) 文字列 `pe` からデータを収集し `lnk_e`ます。 ヒット内で `pe` クエリ文字列の値が異なる場合、このディメンションはデータを収集しません。

AppMeasurementを使用してこのディメンションにデータを送信する場合：

* 目的の値を [`linkName`](/help/implement/vars/config-vars/linkname.md) 変数に入力します。
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"e"`.
* イメージリクエストを送信 [`tl()`](/help/implement/vars/functions/tl-method.md) します。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何であるかが決定されます。 アドビでは、レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
