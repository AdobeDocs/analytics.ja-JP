---
description: クリックしてサイトの外に移動するためのリンクの中で、最も多く使用されているリンクが示されます。これらのリンクは、通常、パートナーや関連会社のサイトです。ただし、外部リンクを組み込んだ任意の場所にすることができます。このレポートを使用して、最も人気のある関連会社のリンクを確認したり、お客様が提供しているとパートナーが主張する、パートナーサイトへのリンク数を検証したりできます。
title: 離脱リンク
topic: Reports
uuid: e1452f04-389d-4aa3-8763-732880284302
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 離脱リンク

クリックしてサイトの外に移動するためのリンクの中で、最も多く使用されているリンクが示されます。これらのリンクは、通常、パートナーや関連会社のサイトです。ただし、外部リンクを組み込んだ任意の場所にすることができます。このレポートを使用して、最も人気のある関連会社のリンクを確認したり、お客様が提供しているとパートナーが主張する、パートナーサイトへのリンク数を検証したりできます。

このページに正しく入力するには、いくつか要件があります。

* 手動のカスタムリンクトラッキングを使用する場合は、*`s.tl()`*&#x200B;リクエストを呼び出す必要があります。その際、中間パラメーターに *e* を設定します。

* 自動カスタムリンクトラッキングを使用する場合は、以下の要件がすべて満たされている必要があります。
* 

   * [s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackexlinks.html) が *true* に設定されている。

   * ユーザーがクリックしたリンクが [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html) 変数内の値に一致しない。
   * [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html) が実装されている場合は、外部リンクがこの変数で設定された値のいずれかに一致している。

* 以上の要件のいずれかを満たしていない場合は、このレポートにヒットが入力されません。

* 
* すべてのカスタムリンクトラッキングヒットと同様、ページビュー数の水増しを避けるために、[s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html) 変数はイメージリクエストから削除されます。
* このレポートは、トレンドおよびランクの両方のフォーマットで表示できます。
* このレポートでは、検索フィルターを使用して特定の行項目を見つけることができます。
* 管理ツールを使用して、他の変数との[内訳](/help/analyze/reports-analytics/reports-customize/breakdowns.md)を作成できます。
* [インスタンス](/help/components/c-variables/c-metrics/metrics-instance.md)は、このレポート内でデフォルトで使用できる唯一の指標です。離脱リンクがクリックされた回数をカウントします。
* このレポートで、日別、週別、月別、四半期別の訪問者を有効にすることができます。ただし、Adobe 担当者のみがこれらを有効にすることができ、追加の費用が必要です。すべてのカスタムリンクトラッキング変数に対して実訪問者を有効にすると、レポートスイートの待ち時間が大幅に増大します。

