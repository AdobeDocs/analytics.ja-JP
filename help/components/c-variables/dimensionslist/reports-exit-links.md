---
description: クリックしてサイトの外に移動するためのリンクの中で、最も多く使用されているリンクが示されます。これらのリンクは、通常、パートナーや関連会社のサイトです。ただし、外部リンクを組み込んだ任意の場所にすることができます。このレポートを使用して、最も人気のある関連会社のリンクを確認したり、お客様が提供しているとパートナーが主張する、パートナーサイトへのリンク数を検証したりできます。
seo-description: クリックしてサイトの外に移動するためのリンクの中で、最も多く使用されているリンクが示されます。これらのリンクは、通常、パートナーや関連会社のサイトです。ただし、外部リンクを組み込んだ任意の場所にすることができます。このレポートを使用して、最も人気のある関連会社のリンクを確認したり、お客様が提供しているとパートナーが主張する、パートナーサイトへのリンク数を検証したりできます。
seo-title: 離脱リンク
solution: Analytics
title: 離脱リンク
topic: レポート
uuid: e1452f04-389d-4aa3-8763-732880284302
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 離脱リンク

クリックしてサイトの外に移動するためのリンクの中で、最も多く使用されているリンクが示されます。これらのリンクは、通常、パートナーや関連会社のサイトです。ただし、外部リンクを組み込んだ任意の場所にすることができます。このレポートを使用して、最も人気のある関連会社のリンクを確認したり、お客様が提供しているとパートナーが主張する、パートナーサイトへのリンク数を検証したりできます。

このページに正しく入力するには、いくつか要件があります。

* 手動のカスタムリンクトラッキングを使用する場合は、*`s.tl()`*&#x200B;リクエストを呼び出す必要があります。その際、中間パラメーターに *e* を設定します。

* 自動カスタムリンクトラッキングを使用する場合は、以下の要件がすべて満たされている必要があります。
* 

   * [s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_trackexlinks) が *true* に設定されている。

   * ユーザーがクリックしたリンクが [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters) 変数内の値に一致しない。
   * [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters) が実装されている場合は、外部リンクがこの変数で設定された値のいずれかに一致している。

* 以上の要件のいずれかを満たしていない場合は、このレポートにヒットが入力されません。

* 
* すべてのカスタムリンクトラッキングヒットと同様、ページビュー数の水増しを避けるために、[s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_pagename) 変数はイメージリクエストから削除されます。
* このレポートは、トレンドおよびランクの両方のフォーマットで表示できます。
* このレポートでは、検索フィルターを使用して特定の行項目を見つけることができます。
* You can create [breakdowns](/help/analyze/reports-analytics/reports-customize/breakdowns.md) with any other variable via Admin Tools.
* [インスタンス](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)は、このレポート内でデフォルトで使用できる唯一の指標です。離脱リンクがクリックされた回数をカウントします。
* このレポートで、日別、週別、月別、四半期別の訪問者を有効にすることができます。ただし、Adobe 担当者のみがこれらを有効にすることができ、追加の費用が必要です。すべてのカスタムリンクトラッキング変数に対して実訪問者を有効にすると、レポートスイートの待ち時間が大幅に増大します。

