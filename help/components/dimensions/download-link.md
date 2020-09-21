---
title: ダウンロードリンク
description: ダウンロードリンクの名前。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '180'
ht-degree: 100%

---


# ダウンロードリンク

「ダウンロードリンク」ディメンションは、サイトに実装されたダウンロードリンクの名前をレポートします。このディメンションは、次のようなダウンロードリンクに関する訪問者の動作を詳しく知りたい場合に役立ちます。

* サイトから最も頻繁にダウンロードされているファイルを特定します。
* あるファイルが、特定の期間内でより頻繁にダウンロードされているかを把握します。
* 訪問者が提供される場合、様々なファイルタイプをダウンロードしていることを検証します。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストでの `lnk_d` 値を持つ `pe` クエリ文字列も持つヒットについて、 ](/help/implement/validate/query-parameters.md) クエリ文字列 [`pev2` からデータを収集します。ヒット内で `pe` クエリ文字列の値が異なる場合、このディメンションはデータを収集しません。

AppMeasurement を使用してこのディメンションにデータを送信する場合：

* 目的の値を [`linkName`](/help/implement/vars/config-vars/linkname.md) 変数に入力します。
* [`linkType`](/help/implement/vars/config-vars/linktype.md) 変数を `"d"` に設定します。
* [`tl()`](/help/implement/vars/functions/tl-method.md) イメージリクエストを送信します。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
