---
title: カスタムリンク
description: カスタムリンクの名前。
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# カスタムリンク

「カスタムリンク」ディメンションは、サイトに実装されたカスタムリンクの名前をレポートします。 このディメンションは、訪問者が最もクリックするリンクのタイプを理解したい場合に役立ちます。

## このディメンションにデータを入力する

このディメンションは、の値を持つ [`pev2` クエリ文字列も持つヒットについて、クエリリクエストの](/help/implement/validate/query-parameters.md) 文字列 `pe` からデータを収集し `lnk_o`ます。 ヒット内で `pe` クエリ文字列の値が異なる場合、このディメンションはデータを収集しません。

AppMeasurementを使用してこのディメンションにデータを送信する場合：

* 目的の値を [`linkName`](/help/implement/vars/config-vars/linkname.md) 変数に入力します。
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"o"`.
* イメージリクエストを送信 [`tl()`](/help/implement/vars/functions/tl-method.md) します。

## 分析コード値

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション値が何かを決定します。 アドビでは、レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
