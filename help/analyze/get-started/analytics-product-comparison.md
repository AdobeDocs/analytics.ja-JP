---
description: 必要システム構成と、Analysis Workspace、Report Builder、Data Warehouse、Data Workbench の比較
title: Analytics 製品の比較と必要システム構成
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: ht
source-wordcount: '340'
ht-degree: 100%

---

# Analytics 製品の比較と必要システム構成

このページでは、Adobe Analytics の各種製品（Analysis Workspace、Report Builder、Data Warehouse、データフィード、および Analytics API 2.0）の比較を示します。

使用すべき Adobe Analytics 製品について詳しくは、[使用する Adobe Analytics ツールの検討](/help/analyze/get-started/which-analytics-tool.md)を参照してください。

| 製品名とヘルプリンク | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [データフィード](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **アクセス方法** | [ブラウザー](/help/analyze/get-started/sys-reqs.md) | [Windows 用 MS Excel](/help/analyze/legacy-report-builder/setup/system-requirements.md) | ブラウザーを使用してセットアップします。[詳細情報](/help/analyze/get-started/sys-reqs.md) | ブラウザーを使用してセットアップします。[詳細情報](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API ツール。Adobe Developer の資格情報でログインします。[詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **データの精度** | 集計 | 集計 | 集計 | ヒット | 集計 |
| **Experience Cloud ID（ECID）が使用可能** | × | × | ○ | ○ | × |
| **タイムスタンプが使用可能** | × | × | × | ○ | × |
| **処理レベル** | 完全処理 | 完全処理済みで、個別の[リアルタイムレポートを使用](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) | 完全処理 | 完全処理 | 完全処理 |
| **管理ボットフィルタデータを含む** <br> [詳細情報](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | × | ○（個別のボットレポート） | × | × | × |
| **トラフィックが少ない（ユニークが超過しました）** <br> [詳細情報](/help/technotes/low-traffic.md) | ○ | ○ | × | × | ○ |
| **表示される行数制限（ページ分割前）** | 400 | 50000 | 制限なし | 制限なし | 50000 |
| **複数のレポートスイート** | [○](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | ○ | × | ○ | × | ○ |
| **分類の数** | 制限なし | ～ 2 | 制限なし | 制限なし | 制限なし（複数のクエリに対して実行） |
| **セグメント化** <br> [詳細情報](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | ○ | ○ | ○（[制限あり](/help/components/segmentation/seg-reference/seg-compatibility.md)） | × | ○ |
| **計算指標** <br> [詳細情報](/help/components/c-calcmetrics/cm-overview.md) | ○（[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) あり） | ○（Attribution あり） | ○ | × | ○（[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) あり） |
| **マーケティングチャネル** <br> [詳細情報](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | ○ | ○ | ○ | ○ — [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | ○ |
| **コホート分析** | [○](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | ○ | × | × | × |
| **アトリビューション** | ○（[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) あり） | 制限あり | × | × | ○（[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) あり） | × |
| **キュレーション** <br> [詳細情報](/help/analyze/analysis-workspace/curate-share/curate.md) | ○ - プロジェクトおよび仮想レポートスイート | × | × | × | ○ - 仮想レポートスイートのみ |
| **プロジェクトの共有** <br> [詳細情報](/help/analyze/analysis-workspace/curate-share/share-projects.md) | はい（プロジェクトロールあり） | ○ | × | × | × |
| **配信予定** | ○ | ○ | ○ | ○ | × |
| **配信先** | 電子メール | 電子メール、FTP、SFTP、[Microsoft PowerBI への公開](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3、Google Cloud Platform、Azure SAS、Azure RBAC、メール | Amazon S3、Azure RBAC、Azure SAS、Google Cloud Platform | - |
| **仮想レポートスイートのレポート時間処理** <br> [詳細情報](/help/components/vrs/vrs-report-time-processing.md) | ○ | × | × | × | ○ |
