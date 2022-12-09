---
description: 以下の表に、Analysis Workspace、Reports & Analytics、Report Builder、Data Warehouse、および Data Workbench の機能の比較と必要システム構成を示します。
title: Analytics 製品の比較と必要システム構成
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 94%

---

# Analytics 製品の比較と必要システム構成

このページでは、Adobe Analytics の各種製品（Analysis Workspace、Reports &amp; Analytics、Report Builder、Data Warehouse、Data Workbench、データフィード、Analytics API 2.0）の比較を示します。

使用するAdobe Analytics製品について詳しくは、 [使用するAdobe Analyticsツールの検討](/help/admin/get-started/which-analytics-tool.md).

| 製品名とヘルプリンク | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html?lang=ja) | [データフィード](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **アクセス方法** | [ブラウザー](/help/admin/get-started/sys-reqs.md) | [ブラウザー](/help/admin/get-started/sys-reqs.md) | [Windows 用 MS Excel](/help/analyze/report-builder/setup/system-requirements.md) | ブラウザーを使用してセットアップします。[詳細情報](/help/admin/get-started/sys-reqs.md) | [Windows 64 ビット](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=ja) | ブラウザーを使用してセットアップします。[詳細情報](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API ツール。Adobe Developerの資格情報を使用してログインします。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **データの精度** | 集計 | 集計 | 集計 | 集計 | ヒット | ヒット | 集計 |
| **Experience Cloud ID（ECID）が使用可能** | × | × | × | ○ | ○ | ○ | × |
| **タイムスタンプが使用可能** | × | × | × | × | ○ | ○ | × |
| **処理レベル** | 完全処理 | 完全処理済みで、個別の[リアルタイムレポートを使用](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | 完全処理済みで、個別の[リアルタイムレポートを使用](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | 完全処理 | 完全処理 | 完全処理 | 完全処理 |
| **管理ボットフィルタデータを含む** <br> [詳細情報](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | × | ○（個別のボットレポート） | ○（個別のボットレポート） | × | × | × | × |
| **トラフィックが少ない（ユニークが超過しました）** <br> [詳細情報](/help/technotes/low-traffic.md) | ○ | ○ | ○ | × | × | × | ○ |
| **表示される行数制限（ページ分割前）** | 400 | 200 | 50000 | 制限なし | 制限なし | 制限なし | 50000 |
| **複数のレポートスイート** | [○](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | ○（制限あり） | ○ | × | ○ | × | ○ |
| **分類の数** | 制限なし | ～ 2 | ～ 2 | 制限なし | 制限なし | 制限なし | 制限なし（複数のクエリに対して実行） |
| **セグメント化** <br> [詳細情報](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | ○ | ○ | ○ | ○（[制限あり](/help/components/segmentation/seg-reference/seg-compatibility.md)） | ○ | × | ○ |
| **計算指標** <br> [詳細情報](/help/components/c-calcmetrics/cm-overview.md) | ○（[Attribution IQ あり](/help/analyze/analysis-workspace/attribution/overview.md)） | ○ | ○ | × | ○ | × | ○（[Attribution IQ あり](/help/analyze/analysis-workspace/attribution/overview.md)） |
| **マーケティングチャネル** <br> [詳細情報](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | ○ | ○ | ○ | ○ | ○ | ○ — [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | ○ |
| **コホート分析** | [○](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | × | × | × | ○ | × | × |
| **アトリビューション** | ○（[Attribution IQ あり](/help/analyze/analysis-workspace/attribution/overview.md)） | 制限あり | 制限あり | × | ○ | × | ○（[Attribution IQ あり](/help/analyze/analysis-workspace/attribution/overview.md)） |
| **Virtual Analyst の機能** <br> [詳細情報](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | ○ | × | × | × | × | × | ○ |
| **キュレーション** <br> [詳細情報](/help/analyze/analysis-workspace/curate-share/curate.md) | ○（プロジェクトと VRS） | × | × | × | × | × | ○（VRS のみ） |
| **プロジェクトの共有** <br> [詳細情報](/help/analyze/analysis-workspace/curate-share/share-projects.md) | はい（プロジェクトロールあり） | ○ | ○ | × | ○ | × | × |
| **配信予定** | ○ | ○ | ○ | ○ | × | ○ | × |
| **配信先** | 電子メール | 電子メール | 電子メール、FTP、SFTP、[Microsoft PowerBI への公開](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | 電子メール、 FTP.SFTP、Azure Blob、Amazon S3 など、追加の宛先サポートについては、カスタマーケアにお問い合わせください。 | - | FTP、SFTP、Azure Blob、Amazon S3 | - |
| **VRS レポートの時間処理** <br> [詳細情報](/help/components/vrs/vrs-report-time-processing.md) | ○ | × | × | × | × | × | ○ |
