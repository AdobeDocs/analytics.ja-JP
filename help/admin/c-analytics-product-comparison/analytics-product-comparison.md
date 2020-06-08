---
description: 以下の表に、Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse、および Data Workbenchの 機能の比較と必要システム構成を示します。
title: Analytics 製品の比較と必要システム構成
translation-type: tm+mt
source-git-commit: 9265fb410b20a764ecc86c56b453b045122fcd05
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 73%

---


# Analytics 製品の比較と必要システム構成

必要システム構成と、分析ワークスペース、Reports &amp; Analytics、Ad Hoc分析、Report Builder、Data WarehouseおよびData Workbenchの比較。

どの Adobe Analytics 製品を使用するかについて詳しくは、[こちら](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)に移動します。

| 製品名とヘルプリンク | [Analysis Workspace](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/getting-started.html) | [Ad Hoc Analysis](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/ad-hoc-analysis/adhoc-home.html) | [Report Builder](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/ja-JP/analytics/export/data-warehouse/data-warehouse.translate.html) | [Data Workbench](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/home.html) |
|---|---|---|---|---|---|---|
| **アクセス方法** | 強力なカスタム分析プロジェクトを構築し、インサイトをデモクラタイズ（民主化）するブラウザーソリューション | デジタル分析のブラウザーソリューション | 高度なデジタル分析を実行する Java ベースのツール | Reports &amp; Analytics のデータからカスタムリクエストを構築し、視覚的なレポートを作成する Microsoft Excel のアドイン | .csv 形式のレポートを生成するブラウザーソリューション。Tableau 形式のファイルを生成可能 | カスタムのアトリビューションモデル、予測分析、あらゆる角度からの顧客分析など、高度な分析機能を備えたマルチチャネル分析ツール |
| **レポートの分類** | 制限なし | 最大 2 個の相関関係 | 制限なし | 最大 2 個の相関関係 | 無制限に分類が可能（セグメントによる分類） | 制限なし |
| **セグメントの比較** | 制限なし | 最大 2 個のセグメント | 制限なし | 制限なし（データリクエストスタッキング） | 1 個のセグメントの呼び出しの後におこなわれる場合です。複数のセグメント（スタック）をサポート | 制限なし |
| **行の出力制限** | 400 | 200 | 50,000 | 50,000 | 制限なし | カスタマイズ可能 |
| ****&#x200B;ユニーク値の制限（eVar／prop レポート内） | 50 万～200 万 | 50 万～200 万 | 50 万～200 万 | 50 万～200 万 | 制限なし | カスタマイズ可能 |
| **ファネル／パス** | はい： [フォールアウト](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/[フロー](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [○](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/reports.html) | [○](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-reports-paths.html) | ○ | × | ○ |
| **高度なカスタマージャーニー分析** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-landing.html) | × | ○ | × | × | ○ |
| **コホート分析** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | × | × | × | × | ○ |
| **高度なアトリビューション** | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | 制限あり - 最初／最後／線形 | 制限あり - 最初／最後／線形 | 制限あり - 最初／最後／線形 | 制限あり - 最初／最後／線形 | ○ |
| **ビジュアライゼーションの拡張オプション** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | × | ○ | ○ | × | ○ |
| **レイアウトのカスタマイズ** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) | ○ - [ダッシュボード](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | × | [○](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | 分類または指標による結果の並べ替え | ○ |
| ****&#x200B;プロジェクトのキュレーション（非アナリストを対象とする簡潔なレポート） | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html) | × | × | ○ | × | ○ |
| **プロジェクトの共有** | [はい： すべて/任意のユーザー](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html) | [はい： すべて/任意のユーザー](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | Ad Hoc Analysis ユーザーのみ | はい： すべて/任意のユーザー | × | ○ |
| **予定レポートの配信** | [○](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [○](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | [○](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-schedule.html) | [○](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/t-schedule-a-data-request.html) | ○ | ○ |
| **必要システム構成** | <br>[ブラウザの詳細…](https://docs.adobe.com/content/help/ja-JP/analytics/admin/sys-reqs.html) | <br>[ブラウザの詳細…](https://docs.adobe.com/content/help/ja-JP/analytics/admin/sys-reqs.html) | <br>[Java詳細情報…](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-getting-started.html) | Windows、MS Excel<br>[詳細…](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | ブラウザー、.csv ファイルを開くことのできるプログラム（MS Excel など）。Tableau 形式のファイルを生成可能 | Windows 64 bit, good graphics adapter for OpenGL 3.2 [More...](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html) |
| **仮想レポートスイート（レポート時間処理）の互換性** | ○ | ○ | ○ | ○ | × | ○? |
| **複数のレポートスイート** | ○ | × | × | × | × | ○? |
| **計算指標** | ○ | ○ | ○ | ○ | ○ | ○ |
| **マーケティングチャネルの互換性** | ○ | ○ | ○ | ○ | ? | ? |
| **精度のレベル** |  |  |  |  |  |  |
| **異常値検出** | ○ | × |  |  |  |  |
| **貢献度分析** | ○ | × | × | × | × | ○ |
| **セグメントタイプ** |  |  |  |  |  |  |