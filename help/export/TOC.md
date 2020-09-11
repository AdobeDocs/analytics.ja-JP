---
product: analytics
audience: end-user
user-guide-title: Analytics 書き出しガイド
breadcrumb-title: Export Guide
user-guide-description: Get data out of Adobe Analytics. Use Data Feeds to receive an hourly or daily export of raw data. Retrieve a spreadsheet output of data using Data Warehouse.
user-guide-url: /content/help/en/analytics/export/home.html
translation-type: tm+mt
source-git-commit: 4cfcb8a8c86d86d0a3a5b038406be9e2b1980ab3
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 95%

---


# Analytics 書き出しガイド {#export}

+ [Analytics エクスポートホーム](home.md)
+ Analytics データフィード {#analytics-data-feed}
   + [データフィードの概要](analytics-data-feed/data-feed-overview.md)
   + [データフィードの作成または編集](analytics-data-feed/create-feed.md)
   + [データフィードの管理](analytics-data-feed/df-manage-feeds.md)
   + [データフィードジョブの管理](analytics-data-feed/df-manage-jobs.md)
   + データフィードの内容 {#data-feed-contents}
      + [データフィードの内容についての概要](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [計算指標](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [データ列リファレンス](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [ページイベント参照](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [モバイル属性参照](analytics-data-feed/c-df-contents/mobile-attributes-lookup.md)
      + [特殊文字](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [到着が遅れたヒット](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [データフィードに関する FAQ](analytics-data-feed/df-faq.md)
   + [データフィードのベストプラクティス](analytics-data-feed/data-feeds-best-practices.md)
   + [データフィードのトラブルシューティング](analytics-data-feed/feed-troubleshooting.md)
   + [ジョブのトラブルシューティング](analytics-data-feed/jobs-troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Data Warehouse の概要](data-warehouse/data-warehouse.md)
   + [Data Warehouse ユーザーグループの追加](data-warehouse/t-dw-group.md)
   + [Data Warehouse リクエストの作成](data-warehouse/t-dw-create-request.md)
   + [リクエスト配信時間](data-warehouse/delivery-time.md)
   + [Tableau 形式のデータファイル](data-warehouse/t-tableau.md)
   + [指標で並べ替え](data-warehouse/sorting-by-metric.md)
   + [定期的なリクエストのスケジュール設定](data-warehouse/dw-schedule-recurring.md)
   + [Data Warehouse リクエストの管理](data-warehouse/data-warehouse-requests-manage.md)
   + [Data Warehouse でサポートされるコンポーネント](data-warehouse/component-support.md)
   + [Data Warehouse セグメントと互換性のないディメンション](data-warehouse/dw-dimensions-incompatible-dwsegments.md)
   + [Data Warehouse のベストプラクティス](data-warehouse/data-warehouse-bp.md)
+ FTP と SFTP {#ftp-and-sftp}
   + [Adobe Experience Cloud での FTP および SFTP の使用](ftp-and-sftp/ftp-overview.md)
   + アドビがホストする FTP アカウントの設定 {#set-up-ftp-accounts}
      + [FTP アカウントの設定 - 概要](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [分類](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [データソース](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [Data Connectors](ftp-and-sftp/c-set-up-ftp-accounts/ftp-genesis.md)
      + [データフィード](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
      + [Ad Hoc Analysis が配信するレポート](ftp-and-sftp/c-set-up-ftp-accounts/ftp-discover-reports.md)
      + [Data Warehouse が配信するレポート](ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)
      + [Report Builder が配信するレポート](ftp-and-sftp/c-set-up-ftp-accounts/ftp-arb-reports.md)
      + [FTP を使用した Engineering Services エンゲージメント](ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)
   + [FTP の制限とデータ保持期間](ftp-and-sftp/ftp-limits.md)
   + [FTP データおよび FTP アカウントの削除](ftp-and-sftp/ftp-delete.md)
   + [削除された FTP データおよび FTP アカウントの復元](ftp-and-sftp/ftp-restore.md)
   + [Adobe FTP サーバーのアップグレード](ftp-and-sftp/ftp-upgrade.md)
   + [FTP Passive モードを使用](ftp-and-sftp/ftp-passive.md)
   + [FTP 処理時間](ftp-and-sftp/ftp-processing.md)
   + セキュアファイル転送プロトコル {#secure-file-transfer-protocol}
      + [セキュアファイル転送プロトコル - 概要](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [SFTP を使用したアドビの FTP アカウントへの接続](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [SFTP を使用した外部 FTP アカウントへのアドビデータの送信](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [SFTP サーバーへの Data Warehouse リクエストの送信](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [パスワードなしでの SFTP 経由でのアドビへの接続](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Analysis Workspaceダウンロード](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/download-send.html)
+ [Adobe Analytics API ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/home.html)
