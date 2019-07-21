---
description: page_event の値に基づいてヒットソースを判別する参照テーブル。
keywords: データフィード;ヒット、source
seo-description: page_event の値に基づいてヒットソースを判別する参照テーブル。
seo-title: ヒットソース参照
solution: Analytics
title: ヒットソース参照
topic: Reports and Analytics
uuid: b4ef2366- a7c3-421b-8dc6-279706fe277f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ヒットソース参照

page_event の値に基づいてヒットソースを判別する参照テーブル。

| ID | ヒットソース |
|---|---|
| 1 | タイムスタンプの渡されていないページビューまたは追跡リンク（タイムスタンプなしのレポートスイート） |
| 2 | タイムスタンプの渡されているページビューまたは追跡リンク（タイムスタンプ付きのレポートスイート） |
| 3 | ヒットタイムスタンプ付きのライブログファイル（履歴ログファイルではない） |
| 4 | 未使用 |
| 5 | 「汎用」（e コマースとも言います）データソース（現在のデータソースなど） |
| 6 | フル（履歴）ログファイル（ライブログファイルではない） |
| 7 | transactionid／customerid データソースファイル |
| 8 | SCM（SearchCenter+）データソース |
| 9 | Adobe Social 概要指標 |

