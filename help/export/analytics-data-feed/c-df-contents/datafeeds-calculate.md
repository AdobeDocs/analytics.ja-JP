---
description: データフィードを使用して一般的な指標を計算する方法について説明します。
keywords: データフィード;ジョブ;指標;列の前;列の後;ボット;日付フィルタリング;イベント文字列; 共通;数式
title: 計算指標
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
source-git-commit: adee2f1013cfd2ae231e3133b5a5327b8792bd16
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 76%

---

# データフィードを使用した一般的な指標の計算

データフィードを使用して一般的な指標を計算する方法について説明します。

>[!NOTE]
>
>通常はAnalysis Workspaceから除外されるヒットが、データフィードに含まれます。 次の条件を関連するクエリに追加することを検討してください。
>
>* **`exclude_hit`**:Analysis Workspaceには、`exclude_hit = 0` の場所にあるデータのみが含まれます。
>* **`customer_perspective`**：モバイルバックグラウンドヒットを含む仮想レポートスイートを使用しない限り、Analysis Workspaceには `customer_perspective = 0` のデータのみが含まれます。
>* **`hit_source`**：データソースのデータには、生データとAnalysis Workspaceの違いが含まれている場合があります。 データソースからのヒットを除外する場合は、`hit_source = 5,7,8,9` の条件を満たすすべての行を除外します。

## ページビュー数

1. 値が `post_pagename` または `post_page_url` に含まれる行の数をカウントします。

## 発生件数

1. 合計行数をカウントします。

## 訪問数

1. `post_visid_high`、`post_visid_low`、`visit_num`、および `visit_start_time_gmt` を連結します。
1. 一意の値の数をカウントします。

>[!TIP]
>
>インターネットの不規則性やシステムの不規則性、またはカスタム訪問者 ID の使用によって、別の訪問時に同じ `visit_num` 値を使用することはほとんどありません。オプションですが、訪問をカウントする際には `visit_start_time_gmt` を使用して、その訪問がカウントされるようにします。

## 訪問者数

Adobeがユニーク訪問者の特定に使用するすべての手段（カスタム訪問者 ID、Experience Cloud ID サービスなど）は、最終的に `post_visid_high` と `post_visid_low` の値として計算されます。 これらの 2 つの列を連結することで、どのようにしてユニーク訪問者として識別されたかに関係なく、ユニーク訪問者を識別する際の標準として使用できます。アドビがユニーク訪問者を識別するために使用した方法を理解するには、列 `post_visid_type` を使用します。

1. `post_visid_high` と `post_visid_low` を連結します。
2. 一意の値の数をカウントします。

## カスタムリンク、ダウンロードリンクまたは離脱リンク

1. 次の行数をカウントします。
   * `post_page_event = 100`（カスタムリンクの場合）
   * `post_page_event = 101`（ダウンロードリンクの場合）
   * `post_page_event = 102`（離脱リンクの場合）

## カスタムイベント

すべての指標は、`post_event_list` でコンマ区切りの整数としてカウントされます。`event.tsv` を使用して、数値を目的のイベントと照合します。例えば、`post_event_list = 1,200` は、ヒットに購入イベントとカスタムイベント 1 が含まれていることを示します。

1. `post_event_list` 内にイベント参照の値が出現する回数をカウントします。

## 滞在時間

ヒットは、最初に訪問ごとにグループ化してから、訪問内でのヒット数に従って並べ替える必要があります。

1. `post_visid_high`、`post_visid_low`、`visit_num`、および `visit_start_time_gmt` を連結します。
2. この連結された値で並べ替えてから、2 番目の並べ替え条件 `visit_page_num` を適用します。
3. ヒットが 1 回の訪問で最後のヒットでない場合は、後続の `post_cust_hit_time` の値から `post_cust_hit_time` の値を引きます。
4. この数は、ヒットに費やした時間（秒）です。フィルターを適用して、ディメンション項目やイベントに焦点を当てることができます。

## 注文件数、数量、売上高

`currency` の値がレポートスイートの通貨と一致しない場合は、その日のコンバージョン率を使用して換算されます。`post_product_list`列では換算後の通貨値が使用されるので、この列の通貨はすべてのヒットで同じになります。

1. `duplicate_purchase = 1` の行をすべて排除します。
2. `event_list` に購入イベントが含まれる行のみを含めます。
3. `post_product_list` 列を解析してすべての価格データを抽出します。`post_product_list` 列の形式は `s.products` 変数と同じになります。
4. 目的の指標を計算します。
   * 行数をカウントして注文数を計算する
   * 製品文字列の `quantity` の数を合計して数量を計算する
   * 製品文字列の `price` の数を合計して売上高を計算する
