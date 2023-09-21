---
title: 離脱リンク
description: 離脱リンクの名前。
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 91%

---

# 離脱リンク

「出口リンク」 [ディメンション](overview.md) は、サイトに実装された出口リンクの名前をレポートします。 このディメンションは、サイト外のドメインを指すどのリンクが最も人気があるかを把握したい場合に役立ちます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストでの `lnk_e` 値を持つ `pe` クエリ文字列も持つヒットについて、クエリ文字列 [`pev2`](/help/implement/validate/query-parameters.md) からデータを収集します。ヒット内で `pe` クエリ文字列の値が異なる場合、このディメンションはデータを収集しません。

AppMeasurement を使用してこのディメンションにデータを送信する場合は、`"e"` のリンクタイプ引数を持つ [`tl()`](/help/implement/vars/functions/tl-method.md) イメージリクエストを送信します。リンク名の引数に必要な値を入力します。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
