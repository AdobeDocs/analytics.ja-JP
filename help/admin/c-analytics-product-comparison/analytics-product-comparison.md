---
description: 以下の表に、Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse、および Data Workbenchの 機能の比較と必要システム構成を示します。
title: Analytics 製品の比較と必要システム構成
translation-type: tm+mt
source-git-commit: cb3948f03e65edf18b7f3c54c891b77629b41dc0
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 83%

---


# Analytics 製品の比較と必要システム構成

必要システム構成と、Analysis Workspace、Reports &amp;Analytics、Report Builder、Data warehouse、Data Workbench、AnalyticsAPI 2.0.、データフィード、Customer Journey Analyticsの比較。

どの Adobe Analytics 製品を使用するかについて詳しくは、[こちら](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)に移動します。

| 製品名とヘルプリンク | [Analysis Workspace](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/getting-started.translate.html) | [Report Builder](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/ja-JP/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/home.html) | AnalyticsAPI 2.0 | データフィード | Customer Journey Analytics |
|---|---|---|---|---|---|---|
| **アクセス方法** | 強力なカスタム分析プロジェクトを構築し、インサイトをデモクラタイズ（民主化）するブラウザーソリューション | デジタル分析のブラウザーソリューション | .csv 形式のレポートを生成するブラウザーソリューション。Tableau 形式のファイルを生成可能 | カスタムのアトリビューションモデル、予測分析、あらゆる角度からの顧客分析など、高度な分析機能を備えたマルチチャネル分析ツール |  |  |  |
| **レポートの分類** | 制限なし | 最大 2 個の相関関係 | 最大 2 個の相関関係 | 無制限に分類が可能（セグメントによる分類） | 制限なし |  |  |  |
| **セグメントの比較** | 制限なし | 最大 2 個のセグメント | 制限なし （データリクエストのスタック） | 1 個のセグメント. 複数のセグメント（スタック）をサポート | 制限なし |  |  |  |
| **行の出力制限** | 400 | 200 | 50,000 | 制限なし | カスタマイズ可能 |  |  |  |
| ****&#x200B;ユニーク値の制限（eVar／prop レポート内） | 50 万～200 万 | 50 万～200 万 | 50 万～200 万 | 制限なし | カスタマイズ可能 |  |  |  |
| **ファネル／パス** | はい： [フォールアウト](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/[フロー](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/reports.html) | ○ | × | ○ |  |  |  |
| **高度なカスタマージャーニー分析** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/ja-JP/analytics-platform/using/cja-landing.html) | × | × | × | ○ |  |  |  |
| **コホート分析** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | × | × | × | ○ |  |  |  |
| **高度なアトリビューション** | はい： [アトリビューションIQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | 制限あり - 最初／最後／線形 | 制限あり - 最初／最後／線形 | 制限あり - 最初／最後／線形 | ○ |  |  |  |
| **ビジュアライゼーションの拡張オプション** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | × | ○ | × | ○ |  |  |  |
| **レイアウトのカスタマイズ** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) | ○ - [ダッシュボード](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | 分類または指標による結果の並べ替え | ○ |  |  |  |
| ****&#x200B;プロジェクトのキュレーション（非アナリストを対象とする簡潔なレポート） | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html) | × | ○ | × | ○ |  |  |  |
| **プロジェクトの共有** | [はい： すべて/任意のユーザー](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html) | [はい： すべて/任意のユーザー](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/scheduling.html) | はい： すべて/任意のユーザー | × | ○ |  |  |  |
| **予定レポートの配信** | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/scheduling.html) | [○](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/t-schedule-a-data-request.html) | ○ | ○ |  |  |  |
| **必要システム構成** | <br>[ブラウザの詳細…](https://docs.adobe.com/content/help/ja-JP/analytics/admin/sys-reqs.html) | <br>[ブラウザの詳細…](https://docs.adobe.com/content/help/ja-JP/analytics/admin/sys-reqs.html) | Windows、MS Excel<br>[詳細…](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | ブラウザー、.csv ファイルを開くことのできるプログラム（MS Excel など）。Tableau 形式のファイルを生成可能 | Windows 64 bit, good graphics adapter for OpenGL 3.2 [More...](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/install/c-data-workbench-client-install.html) |  |  |  |
| **仮想レポートスイート（レポート時間処理）の互換性** | ○ | ○ | ○ | × | ○? |  |  |  |
| **複数のレポートスイート** | ○ | × | × | × | ○? |  |  |  |
| **計算指標** | ○ | ○ | ○ | ○ | ○ |  |  |  |
| **マーケティングチャネルの互換性** | ○ | ○ | ○ | ? | ? |  |  |  |
| **精度のレベル** |  |  |  |  |  |  |  |  |
| **異常値検出** | ○ | × |  |  |  |  |  |  |
| **貢献度分析** | ○ | × | × | × | ○ |  |  |  |
| **セグメントタイプ** |  |  |  |  |  |  |  |  |