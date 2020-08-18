---
description: 以下の表に、Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse、および Data Workbench の機能の比較と必要システム構成を示します。
title: Analytics 製品の比較と必要システム構成
translation-type: tm+mt
source-git-commit: 8a48a5bd9e7ef38ffc90ecb9c640166bb3ac4405
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 54%

---


# Analytics製品の比較と必要システム構成

このページでは、Adobe Analyticsの各種製品の比較を示します。Analysis Workspace、Reports &amp; Analytics、Report Builder、Data Warehouse、Data Workbench、データフィードおよびAnalytics API 2.0。

どの Adobe Analytics 製品を使用するかについて詳しくは、[こちら](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)に移動します。

| 製品名とヘルプリンク | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/home.html) | [データフィード](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **アクセス方法** | [ブラウザー](/help/admin/sys-reqs.md) | [ブラウザー](/help/admin/sys-reqs.md) | [Windows用MS Excel](/help/analyze/report-builder/setup/system-requirements.md) | ブラウザーを使用してセットアップします。 [詳細情報](/help/admin/sys-reqs.md) | [Windows 64ビット](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/install/c-data-workbench-client-install.html) | ブラウザーを使用してセットアップします。 [詳細情報](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful APIツール。 AdobeI/O資格情報を使用してログインします。 [詳細情報](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **データ精度** | 集計 | 集計 | 集計 | 集計 | ヒット | ヒット | 集計 |
| **Experience CloudID (ECID)が使用可能** | × | × | × | ○ | ○ | ○ | × |
| **使用可能なタイムスタンプ** | × | × | × | × | ○ | ○ | × |
| **処理レベル** | 完全処理済み | フル処理済みで、個別の [リアルタイムレポートを使用](/help/components/c-real-time-reporting/realtime.md) | フル処理済みで、個別の [リアルタイムレポートを使用](/help/components/c-real-time-reporting/realtime.md) | 完全処理済み | 完全処理済み | 完全処理済み | 完全処理済み |
| **管理ボットフィルタデータが含まれています** <br> [詳細情報](/help/admin/admin/bot-removal/bot-removal.md) | × | はい — 個別のボットレポート | はい — 個別のボットレポート | × | × | × | × |
| **トラフィックが少ない（ユニークが超過しました）** <br> [詳細情報](/help/technotes/low-traffic.md) | ○ | ○ | ○ | × | × | × | ○ |
| **表示される行数制限（ページ分割前）** | 400 | 200 | 50000 | 制限なし | 制限なし | 制限なし | 50000 |
| **複数のレポートスイート** | [○](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | ○（制限あり） | ○ | × | ○ | × | ○ |
| **分類の数** | 制限なし | ～ 2 | ～ 2 | 制限なし | 制限なし | 制限なし | 無制限、複数のクエリに対して実行 |
| **セグメント化** <br> [詳細情報](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | ○ | ○ | ○ | ○( [制限あり)](/help/components/segmentation/seg-reference/seg-compatibility.md) | ○ | × | ○ |
| **計算指標** <br> [詳細情報](/help/components/c-calcmetrics/cm-overview.md) | はい、 [Attribution IQあり](/help/analyze/analysis-workspace/attribution/overview.md) | ○ | ○ | × | ○ | × | はい、 [Attribution IQあり](/help/analyze/analysis-workspace/attribution/overview.md) |
| **マーケティングチャネル** <br> [詳細情報](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | ○ | ○ | ○ | ○ | ○ | はい — [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | ○ |
| **コホート分析** | [○](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | × | × | × | ○ | × | × |
| **アトリビューション** | はい、 [Attribution IQあり](/help/analyze/analysis-workspace/attribution/overview.md) | 制限あり | 制限あり | × | ○ | × | はい、 [Attribution IQあり](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Virtual Analystの機能** <br> [詳細情報](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | ○ | × | × | × | × | × | ○ |
| **キュレーション** <br> [詳細情報](/help/analyze/analysis-workspace/curate-share/curate.md) | ○ — プロジェクトとVRS | × | × | × | × | × | ○ - VRSのみ |
| **プロジェクトの共有** <br> [詳細情報](/help/analyze/analysis-workspace/curate-share/share-projects.md) | はい（プロジェクトロールあり） | ○ | ○ | × | ○ | × | × |
| **配信予定** | ○ | ○ | ○ | ○ | × | ○ | × |
| **配信先** | 電子メール | 電子メール | 電子メール、FTP、SFTP、Microsoft PowerBIへ [の公開](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | 電子メール、FTP。 SFTP、Azure Blob、AmazonS3など、追加の宛先サポートについては、カスタマーケアにお問い合わせください。 | - | FTP、SFTP、Azure Blob、AmazonS3 | - |
| **VRSレポートの時間処理** <br> [詳細情報](/help/components/vrs/vrs-report-time-processing.md) | ○ | × | × | × | × | × | ○ |
