---
title: 出口リンク
description: 訪問者がサイトを離れるためにクリックする最も一般的なリンクをレポートします。
translation-type: tm+mt
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# 出口リンク

訪問者がクリックしてサイトを離れる最も一般的なリンクを表示します。 これらのリンクは、通常、パートナーやアフィリエイトのサイトを指し示します。ただし、外部リンクを持つ任意の場所を指定できます。 このレポートを使用して、最も人気のある関連会社のリンクを確認したり、お客様が提供しているとパートナーが主張する、パートナーサイトへのリンク数を検証したりできます。

このページに正しく入力するには、いくつか要件があります。
* 手動のカスタムリンクトラッキングを使用する場合は、中間 `tl()` のパラメーターをに設定してリクエストを実行する必要がありま `e`す。
* 自動カスタムリンクトラッキングを使用する場合は、以下の要件がすべて満たされている必要があります。
   * trackExternalLinks変数 [を有効にする](/help/implement/vars/config-vars/trackexternallinks.md) 。
   * The link the user clicked on must not match any values within the [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) variable.
   * If the [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) variable exists, the external link must match at least one of the values set in this variable.
* 上記の要件のいずれかを満たさない場合、ヒットはこのレポートに入力されません。
* すべてのカスタムリンクトラッキングヒットと同様に、 [pageName](/help/implement/vars/page-vars/pagename.md) 変数はイメージリクエストから削除され、ページビュー指標が膨張するのを防ぎます。
* このレポートは、トレンドおよびランクの両方のフォーマットで表示できます。
* このレポートでは、検索フィルターを使用して特定の行項目を見つけることができます。
* 他の変数を使用し [て分類](/help/analyze/reports-analytics/reports-customize/breakdowns.md) を作成できます。
