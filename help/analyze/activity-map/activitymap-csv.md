---
description: 標準モードで、[!DNL Activity Map]からAnalyticsデータをコンマ区切り値(CSV)ファイルにエクスポートします。
seo-description: 標準モードで、[!DNL Activity Map]からAnalyticsデータをコンマ区切り値(CSV)ファイルにエクスポートします。
seo-title: CSV ファイルへのエクスポート
solution: Analytics
title: CSV ファイルへのエクスポート
topic: Activity Map
uuid: dc6c50c0-57f7-45b8-a4cb-2092a21da529
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# CSV ファイルへのエクスポート

In Standard Mode, export Analytics data from [!DNL Activity Map] to a Comma Separated Values (CSV) file.

ユーザーは、リンククリックデータを他のデータソースと結合するか、他の分析（Excel などで）を実行することが必要になる場合があります。CSV export allows you to obtain all of your [!DNL Activity Map] data for a given page in an easy-to-consume format. ページ用に生成された解析データをフラットなCSVファイルに保存し、ページレポート、ページフローレポート [)およびページ上のリンクデータをエ](/help/analyze/activity-map/activitymap-page-flow.md)クスポートできます [](/help/analyze/activity-map/activitymap-links-report.md) 。 その後、スプレッドシートまたはテキストファイルとして表示したり、別のシステムにデータをインポートしたりできます。

Click the Export icon on the [!DNL Activity Map] toolbar.

[!DNL Activity Map] により、Adobe Analytics ページ名に基づいてファイル名が生成され、日付とタイムスタンプが付加されます（Pagename_DateTime.csv）。このファイルは、対応するブラウザーのデフォルトのダウンロードディレクトリの下に保存されます。

| エクスポート情報 | 説明 |
|---|---|
| ページ指標レポート | ページでの滞在時間、ページのクリック数および合計ページ表示回数を含む、Analytics のページ指標データ。 |
| ページの詳細レポート | 内部エントリまたは外部参照の前のページ、および離脱データをを特定する、ページエントリおよび離脱情報。 |
| ページ上のリンクレポート | 標準モードまたはライブモードの特定のページのリンク情報。 |
