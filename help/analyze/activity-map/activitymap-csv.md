---
description: 標準モードで、Analytics データを Activity Map からコンマ区切り値（CSV）ファイルに書き出します。
title: CSV ファイルへの書き出し
topic: Activity map
uuid: dc6c50c0-57f7-45b8-a4cb-2092a21da529
translation-type: tm+mt
source-git-commit: ee5489798f8c82c563b49b6c96acd1e63a0aa920

---


# CSV ファイルへの書き出し

標準モードで、Analytics データを Activity Map からコンマ区切り値（CSV）ファイルに書き出します。

ユーザーは、リンククリックデータを他のデータソースと結合したり、他の分析（Excelなど）を実行したりする必要がある場合があります。 CSV に書き出すことにより、特定のページのすべての Activity Map データを利用しやすい形式で入手できます。ページ用に生成された解析データをフラットなCSVファイルに保存し、ページレポート、ページフローレポート [、ページ上のリンクの各データをエ](/help/analyze/activity-map/activitymap-page-flow.md)クスポートできます [](/help/analyze/activity-map/activitymap-links-report.md) 。 その後、スプレッドシートや表示ファイルとしてデータを読み込んだり、別のシステムにデータを読み込んだりできます。

Activity Map ツールバーの書き出しアイコンをクリックします。

アクティビティマップは、Adobe Analyticsページ名に基づいてファイル名を生成し、日付とタイムスタンプを付加します。Pagename_DateTime.csv。 このファイルは、対応するブラウザのデフォルトのダウンロードディレクトリに保存されます。

| 書き出し情報 | 説明 |
|---|---|
| ページ指標レポート | ページでの滞在時間、ページのクリック数、合計ページ表示数など、Analyticsのページ指標データ。 |
| ページの詳細レポート | 内部エントリまたは外部参照の前のページ、および離脱データを識別するページエントリと離脱情報。 |
| ページ上のリンクレポート | 標準モードまたはライブモードでの特定のページのリンク情報。 |
