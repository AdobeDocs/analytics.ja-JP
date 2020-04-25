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

ユーザーは、リンククリックデータを他のデータソースと結合するか、他の分析（Excel などで）を実行することが必要になる場合があります。CSV にエクスポートすることにより、特定のページのすべての Activity Map データを利用しやすい形式で入手できます。あるページに関して生成された分析データをフラットな CSV ファイルに保存できるので、 Page Report, [Page Flow Report](/help/analyze/activity-map/activitymap-page-flow.md), and [Links on Page](/help/analyze/activity-map/activitymap-links-report.md) data. その後、スプレッドシートまたはテキストファイルとして表示したり、別のシステムにデータをインポートしたりできます。

Activity Map ツールバーの書き出しアイコンをクリックします。

Activity Map により、Adobe Analytics ページ名に基づいてファイル名が生成され、日付とタイムスタンプが付加されます（Pagename_DateTime.csv）。このファイルは、対応するブラウザーのデフォルトのダウンロードディレクトリの下に保存されます。

| 書き出し情報 | 説明 |
|---|---|
| ページ指標レポート | ページでの滞在時間、ページのクリック数および合計ページ表示回数を含む、Analytics のページ指標データ。 |
| ページの詳細レポート | 内部エントリまたは外部参照の前のページ、および離脱データをを特定する、ページエントリおよび離脱情報。 |
| ページ上のリンクレポート | 標準モードまたはライブモードの特定のページのリンク情報。 |
