---
description: 標準モードで、Analytics データを Activity Map からカンマ区切り値（CSV）ファイルへエクスポートします。
seo-description: 標準モードで、Analytics データを Activity Map からカンマ区切り値（CSV）ファイルへエクスポートします。
seo-title: CSV ファイルへのエクスポート
solution: Analytics
title: CSV ファイルへのエクスポート
topic: Activity Map
uuid: dc6c50c0-57f7-45b8- a4cb-2092a21da529
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# CSV ファイルへのエクスポート

標準モードで、Analytics データを Activity Map からカンマ区切り値（CSV）ファイルへエクスポートします。

ユーザーは、リンククリックデータを他のデータソースと結合するか、他の分析（Excel などで）を実行することが必要になる場合があります。CSV にエクスポートすることにより、特定のページのすべての Activity Map データを利用しやすい形式で入手できます。あるページに関して生成された分析データをフラットな CSV ファイルに保存できるので、 Page Report, [Page Flow Report](/help/analyze/activity-map/activitymap-page-flow.md)), and [Links on Page](/help/analyze/activity-map/activitymap-links-report.md) data. その後、スプレッドシートまたはテキストファイルとして表示したり、別のシステムにデータをインポートしたりできます。

Activity Map ツールバーの「エクスポート」アイコンをクリックします。

Activity Map により、Adobe Analytics ページ名に基づいてファイル名が生成され、日付とタイムスタンプが付加されます（Pagename_DateTime.csv）。このファイルは、対応するブラウザーのデフォルトのダウンロードディレクトリの下に保存されます。

| エクスポート情報 | 説明 |
|---|---|
| ページ指標レポート | ページでの滞在時間、ページのクリック数および合計ページ表示回数を含む、Analytics のページ指標データ。 |
| ページの詳細レポート | 内部エントリまたは外部参照の前のページ、および離脱データをを特定する、ページエントリおよび離脱情報。 |
| ページ上のリンクレポート | 標準モードまたはライブモードの特定のページのリンク情報。 |
