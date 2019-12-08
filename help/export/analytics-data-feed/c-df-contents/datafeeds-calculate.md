---
description: データフィードを使用して一般的な指標を計算する方法について説明します。
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
title: 計算指標
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# データフィードを使用した一般的な指標の計算

データフィードを使用して一般的な指標を計算する方法について説明します。

> [!IMPORTANT] 通常、Adobe Analyticsから除外されるヒットは、データフィードに含まれます。 生データ `exclude_hit > 0` に関するクエリーから除外されたヒットを削除する場合に使用します。 データソースのデータもデータフィードに含まれます。 データソースを除外する場合は、を使用してすべての行を除外しま `hit_source = 5,7,8,9`す。

## ページビュー

1. またはに含まれる値の行数をカウントし `post_pagename` ます `post_page_url`。

## 訪問数

1. 連結 `post_visid_high`、、 `post_visid_low`、お `visit_num`よび `visit_start_time_gmt`。
1. 一意の値の数をカウントします。

> [!NOTE] インターネットの不整合、システムの不整合、またはカスタム訪問者IDの使用で、訪問ごとに同じ値を使用する `visit_num` ことはほとんどありません。 訪問をカ `visit_start_time_gmt` ウントする場合に使用して、これらの訪問が確実にカウントされるようにします。

## 訪問者

個別訪問者（カスタム訪問者ID、Experience Cloud IDサービスなど）を識別するためにアドビが使用するすべての方法の値は、すべて最終的にとの値として計算さ `post_visid_high` れま `post_visid_low`す。 これらの2つの列を連結して、個別訪問者がどのようにして個別訪問者として識別されたかに関係なく、個別訪問者を識別する標準として使用できます。 アドビが個別訪問者を識別するために使用した方法を理解したい場合は、この列を使用しま `post_visid_type`す。

1. とを連 `post_visid_high` 結しま `post_visid_low`す。
2. 一意の値の数をカウントします。

## カスタムリンク、ダウンロードリンクまたは離脱リンク

1. 行数をカウントします。
   * `post_page_event = 100` カスタムリンク
   * `post_page_event = 101` ダウンロードリンク用
   * `post_page_event = 102` 離脱リンク用

## カスタムイベント

すべての指標は、コンマ区切りの整 `post_event_list` 数として列にカウントされます。 数値を `event.tsv` 目的のイベントと照合する場合に使用します。 例えば、ヒットに購 `post_event_list = 1,200` 入イベントとカスタムイベント1が含まれていることを示します。

1. Count the number of times the event lookup value appears in `post_event_list`.

## 滞在時間

ヒットは、最初に訪問別にグループ化し、次に訪問内のヒット数に従って並べ替える必要があります。

1. 連結 `post_visid_high`、、 `post_visid_low`、お `visit_num`よび `visit_start_time_gmt`。
2. この連結された値で並べ替え、2番目の並べ替え基準を適用しま `visit_page_num`す。
3. ヒットが1回の訪問で最後のヒットでない場合は、後続のヒッ `post_cust_hit_time` トの値から値を引きま `post_cust_hit_time` す。
4. この数は、ヒットに費やした時間（秒）です。 フィルターを適用して、ディメンションの値やイベントに焦点を当てることができます。

## 注文件数、数量、売上高

ヒットの値がレポートス `currency` イートの通貨と一致しない場合、その日のコンバージョン率を使用して換算されます。 列では換算さ `post_product_list` れた通貨値が使用されるので、すべてのヒットでこの列の通貨が同じになります。

1. Exclude all rows where `duplicate_purchase = 1`.
2. 購入イベントを含む行 `event_list` のみを含めます。
3. 列を解析し `post_product_list` てすべての価格データを抽出します。 列の形 `post_product_list` 式は変数と同じになり `s.products` ます。
4. 目的の指標を計算します。
   * 注文を計算する行数を数えます
   * 製品文字列の数 `quantity` を合計して単位を計算します
   * 製品文字列内の `price` 数を合計して売上高を計算
