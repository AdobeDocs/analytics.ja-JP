---
description: 以下の表に、Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse、および Data Workbench の機能の比較と必要システム構成を示します。
title: Analytics 製品の比較と必要システム構成
translation-type: tm+mt
source-git-commit: 54d6b4c2993c5b0391b9243c76661db1da4087b8
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 54%

---


# Analytics製品の比較と必要システム構成

このページでは、Adobe Analyticsの各種製品の比較を示します。 Analysis Workspace、レポート&amp;Analytics、Report Builder、Data warehouse、Data Workbench、データフィード、AnalyticsAPI 2.0。

どの Adobe Analytics 製品を使用するかについて詳しくは、[こちら](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)に移動します。

| 製品名とヘルプリンク | [Analysis Workspace](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/ja-JP/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/home.html) | [データフィード](https://docs.adobe.com/content/help/ja-JP/analytics/export/analytics-data-feed/data-feed-overview.html) | [AnalyticsAPI 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **アクセス方法** | [ブラウザー](https://docs.adobe.com/content/help/ja-JP/analytics/admin/sys-reqs.html) | [ブラウザー](https://docs.adobe.com/content/help/ja-JP/analytics/admin/sys-reqs.html) | [Windows用MS Excel](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | ブラウザーを使用してセットアップします。 [詳細情報](https://docs.adobe.com/content/help/ja-JP/analytics/admin/sys-reqs.html) | [Windows 64ビット](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/install/c-data-workbench-client-install.html) | ブラウザーを使用してセットアップします。 [詳細情報](https://docs.adobe.com/content/help/ja-JP/analytics/export/analytics-data-feed/data-feed-overview.html) | RESTful APIツール。 AdobeI/O資格情報を使用してログインします。 [詳細情報](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **データ精度** | 集計 | 集計 | 集計 | 集計 | ヒット | ヒット | 集計 |
| **Experence Cloud ID(ECID)が利用可能** | × | × | × | ○ | ○ | ○ | × |
| **使用可能なタイムスタンプ** | × | × | × | × | ○ | ○ | × |
| **処理レベル** | 完全処理済み | フル処理済みで、個別の [リアルタイムレポートを使用](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | フル処理済みで、個別の [リアルタイムレポートを使用](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | 完全処理済み | 完全処理済み | 完全処理済み | 完全処理済み |
| **管理ボットフィルタデータが含まれています** 。 <br>[詳細](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html) | × | はい — 個別のボットレポート | はい — 個別のボットレポート | × | × | × | × |
| **トラフィックが少ない（ユニークが超過しました）場合** 、 <br>[詳細情報](https://docs.adobe.com/content/help/ja-JP/analytics/technotes/low-traffic.html) | ○ | ○ | ○ | × | × | × | ○ |
| **表示される行数制限（ページ分割前）** | 400 | 200 | 50000 | 制限なし | 制限なし | 制限なし | 50000 |
| **複数のレポートスイート** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) | ○（制限あり） | ○ | × | ○ | × | ○ |
| **分類の数** | 制限なし | ～ 2 | ～ 2 | 制限なし | 制限なし | 制限なし | 無制限、複数のクエリに対して実行 |
| **分類**<br>[の詳細](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) | ○ | ○ | ○ | ○( [制限あり)](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html) | ○ | × | ○ |
| **計算指標**<br>[詳細](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/cm-overview.html) | はい、 [Attribution IQあり](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | ○ | ○ | × | ○ | × | はい、 [Attribution IQあり](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **マーケティングチャネル**<br>[詳細](https://docs.adobe.com/content/help/ja-JP/analytics/components/marketing-channels/c-getting-started-mchannel.html) | ○ | ○ | ○ | ○ | ○ | はい — [va_finder、va_closer](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html) | ○ |
| **コホート分析** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | × | × | × | ○ | × | × |
| **アトリビューション** | はい、 [Attribution IQあり](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | 制限あり | 制限あり | × | ○ | × | はい、 [Attribution IQあり](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Virtual Analyst機能**<br>[詳細](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/virtual-analyst/overview.html) | ○ | × | × | × | × | × | ○ |
| **キュレーション**<br>[詳細](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html) | ○ — プロジェクトとVRS | × | × | × | × | × | ○ - VRSのみ |
| **プロジェクト共有**<br>[の詳細](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | はい（プロジェクトロールあり） | ○ | ○ | × | ○ | × | × |
| **配信予定** | ○ | ○ | ○ | ○ | × | ○ | × |
| **配信先** | 電子メール | 電子メール | 電子メール、FTP、SFTP、Microsoft PowerBIへ [の公開](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/publish-powerbi/power-bi.html) | 電子メール、FTP。 SFTP、Azure Blob、AmazonS3など、追加の宛先サポートについては、カスタマーケアにお問い合わせください。 | - | FTP、SFTP、Azure Blob、AmazonS3 | - |
| **VRSレポートの時間処理**<br>[詳細](https://docs.adobe.com/content/help/ja-JP/analytics/components/virtual-report-suites/vrs-report-time-processing.html) | ○ | × | × | × | × | × | ○ |
