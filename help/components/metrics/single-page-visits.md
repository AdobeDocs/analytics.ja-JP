---
title: 単一ページ訪問
description: 訪問で、'Page'ディメンション項目が変更されなかった回数。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 62%

---


# 単一ページ訪問

*このヘルプページでは、「単一ページ訪問」が指標としてどのように機能するかを説明します。詳しくは、[単一ページ訪問数](../dimensions/single-page-visits.md)ディメンションを参照してください。*

The &#39;Single page visits&#39; metric shows the number of visits where the [Page](../dimensions/page.md) dimension item contained only a single unique value for the entire visit. この指標は、短い訪問を表示したいが、[バウンス](bounces.md)ほど厳しいルールを持たないディメンションのコンテキストで役立ちます。

## この指標の計算方法

この指標は、「ページ」ディメンション項目に訪問全体の単一の一意の値のみが含まれていた訪問回数をカウントします。 訪問者がページをリロードしたり、リンクトラッキングコールを実行した場合でも、単一ページ訪問としてカウントされます。ページディメンションが 2 番目の一意の値に変更されると、その訪問は単一ページ訪問にはなりません。

指標の比較については、「[単一アクセス](single-access.md)」を参照してください。
