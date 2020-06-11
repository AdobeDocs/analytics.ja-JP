---
title: ダウンロードリンク
description: ダウンロードリンクの名前。
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 15%

---


# ダウンロードリンク

「ダウンロードリンク」ディメンションは、サイトに実装されたダウンロードリンクの名前をレポートします。 このディメンションは、次のようなダウンロードリンクに関する訪問者の動作を詳しく知りたい場合に役立ちます。

* サイトから最も頻繁にダウンロードされているファイルを特定します。
* あるファイルが、特定の期間内でより頻繁にダウンロードされているかを把握します。
* 訪問者が提供される場合、様々なファイルタイプをダウンロードしていることを検証します。

## このディメンションにデータを入力する

このディメンションは、の値を持つ [`pev2` クエリ文字列も持つヒットについて、クエリリクエストの](/help/implement/validate/query-parameters.md) 文字列 `pe` からデータを収集し `lnk_d`ます。 ヒット内で `pe` クエリ文字列の値が異なる場合、このディメンションはデータを収集しません。

AppMeasurementを使用してこのディメンションにデータを送信する場合：

* 目的の値を [`linkName`](/help/implement/vars/config-vars/linkname.md) 変数に入力します。
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"d"`.
* イメージリクエストを送信 [`tl()`](/help/implement/vars/functions/tl-method.md) します。

## 分析コード値

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション値が何かを決定します。 アドビでは、レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
