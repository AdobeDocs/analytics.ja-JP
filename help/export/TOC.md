---
product: analytics
audience: end-user
user-guide-title: Analytics 書き出しガイド
breadcrumb-title: 書き出しガイド
user-guide-description: データフィードを使用して生データを書き出し、Data Warehouse を使用してデータのスプレッドシート出力を取得する方法について説明します。 FTP と SFTP を使用してファイルを転送する方法を説明します。
source-git-commit: f68cf0de5e7689d8245572b060a3d81c3bf85072
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 100%

---


# Adobe Analytics エクスポートガイド {#export}

+ [Analytics エクスポートガイド](home.md)
+ [Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=ja)
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
      + [動的検索](analytics-data-feed/c-df-contents/dynamic-lookups.md)
      + [マーチャンダイジング eVar 参照](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [特殊文字](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [到着が遅れたヒット](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [データフィードに関する FAQ](analytics-data-feed/df-faq.md)
   + [データフィードのベストプラクティス](analytics-data-feed/data-feeds-best-practices.md)
   + [データフィードのトラブルシューティング](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Data Warehouse の概要](data-warehouse/data-warehouse.md)
   + [Data Warehouse ユーザーグループの追加](data-warehouse/t-dw-group.md)
   + Data Warehouse リクエストの作成 {#dw-create-request}
      + [Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)
      + [一般設定](/help/export/data-warehouse/create-request/dw-general-settings.md)
      + [レポートを作成](/help/export/data-warehouse/create-request/dw-request-build-report.md)
      + [レポートの宛先](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
      + [レポートオプション](/help/export/data-warehouse/create-request/dw-request-report-options.md)
      + [スケジュールオプション](/help/export/data-warehouse/create-request/dw-request-scheduling.md)
      + [通知メール](/help/export/data-warehouse/create-request/dw-request-email.md)
   + [リクエスト配信時間](data-warehouse/delivery-time.md)
   + [Tableau 形式のデータファイル](data-warehouse/t-tableau.md)
   + [指標で並べ替え](data-warehouse/sorting-by-metric.md)
   + [Data Warehouse リクエストの管理](data-warehouse/data-warehouse-requests-manage.md)
   + [Data Warehouse でサポートされるコンポーネント](data-warehouse/component-support.md)
   + [Data Warehouse に関するよくある質問](data-warehouse/faq.md)
   + [Data Warehouse のベストプラクティス](data-warehouse/data-warehouse-bp.md)
+ FTP と SFTP {#ftp-and-sftp}
   + [Adobe Experience Cloud での FTP および SFTP の使用](ftp-and-sftp/ftp-overview.md)
   + アドビがホストする FTP アカウントの設定 {#set-up-ftp-accounts}
      + [FTP アカウントの設定 - 概要](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [分類](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [データソース](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [データフィード](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
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
      + [SFTP サービスのアップグレード - FAQ](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [セキュアファイル転送プロトコル - 概要](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [SFTP を使用したアドビの FTP アカウントへの接続](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [SFTP を使用した外部 FTP アカウントへのアドビデータの送信](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [SFTP サーバーへの Data Warehouse リクエストの送信](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [パスワードなしでの SFTP 経由でのアドビへの接続](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Analysis Workspace ダウンロード](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=ja)
+ [Adobe Analytics API ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=ja)
