---
title: 離脱リンク
description: 離脱リンクの名前。
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 75%

---

# 離脱リンク

「離脱リンク」 [ ディメンション ](overview.md) は、サイトに実装された離脱リンクの名前をレポートします。 このディメンションは、サイト外のドメインを指すどのリンクが最も人気があるかを把握したい場合に役立ちます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストでの `lnk_e` 値を持つ `pe` クエリ文字列も持つヒットについて、クエリ文字列 [`pev2`](/help/implement/validate/query-parameters.md) からデータを収集します。`pe` クエリ文字列のヒットに異なる値が含まれる場合、このディメンションはデータを収集しません。 このディメンションの最大長は 100 バイトです。

AppMeasurement を使用してこのディメンションにデータを送信する場合は、`"e"` のリンクタイプ引数を持つ [`tl()`](/help/implement/vars/functions/tl-method.md) イメージリクエストを送信します。リンク名の引数に必要な値を入力します。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
