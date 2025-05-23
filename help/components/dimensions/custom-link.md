---
title: カスタムリンク
description: カスタムリンクの名前。
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 75%

---

# カスタムリンク

「カスタムリンク」 [ ディメンション ](overview.md) は、サイトに実装されたカスタムリンクの名前をレポートします。 このディメンションは、訪問者が最もクリックするリンクのタイプを理解したい場合に役立ちます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストでの `lnk_o` 値を持つ `pe` クエリ文字列も持つヒットについて、クエリ文字列 [`pev2`](/help/implement/validate/query-parameters.md) からデータを収集します。`pe` クエリ文字列のヒットに異なる値が含まれる場合、このディメンションはデータを収集しません。 このディメンションの最大長は 100 バイトです。

AppMeasurement を使用してこのディメンションにデータを送信する場合は、`"o"` のリンクタイプ引数を持つ [`tl()`](/help/implement/vars/functions/tl-method.md) イメージリクエストを送信します。リンク名の引数に必要な値を入力します。

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。レポートのニーズに基づいて、リンクを意味のあるカテゴリにグループ化することをお勧めします。
