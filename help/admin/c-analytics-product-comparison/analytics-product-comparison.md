---
description: 以下の表に、Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse、および Data Workbenchの 機能の比較と必要システム構成を示します。
title: Analytics 製品の比較と必要システム構成
uuid: 988eab20-aa94-4eae-ae4a-5f2b70afa5b3
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# Analytics 製品の比較と必要システム構成

以下の表に、Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse、および Data Workbenchの 機能の比較と必要システム構成を示します。

どの Adobe Analytics 製品を使用するかについて詳しくは、[こちら](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)に移動します。

<table id="table_8A42BE3253024552A170F6471B1E4D1D"> 
 <tbody> 
  <tr> 
   <td> <b>製品名とヘルプリンク</b> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/analysis-workspace-features.translate.html"> Analysis Workspace </a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/reports-analytics/getting-started.translate.html"> Reports &amp; Analytics </a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/ad-hoc-analysis/adhoc-home.html"> Ad Hoc Analysis </a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/report-builder/home.html"> Report Builder </a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/export/data-warehouse/data-warehouse.html"> Data Warehouse </a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/data-workbench/using/home.html"> Data Workbench </a> </td> 
  </tr> 
  <tr> 
   <td> <b>アクセス方法</b> </td> 
   <td> 強力なカスタム分析プロジェクトを構築し、インサイトをデモクラタイズ（民主化）するブラウザーソリューション </td> 
   <td> デジタル分析のブラウザーソリューション </td> 
   <td> 高度なデジタル分析を実行する Java ベースのツール </td> 
   <td> Reports &amp; Analytics のデータからカスタムリクエストを構築し、視覚的なレポートを作成する Microsoft Excel のアドイン </td> 
   <td colname="col06"> <span class="filepath">.csv</span> 形式のレポートを生成するブラウザーソリューション。Tableau 形式のファイルを生成可能 </td> 
   <td colname="col6"> カスタムのアトリビューションモデル、予測分析、あらゆる角度からの顧客分析など、高度な分析機能を備えたマルチチャネル分析ツール </td> 
  </tr> 
  <tr> 
   <td> <b>レポートの分類</b> </td> 
   <td> 制限なし </td> 
   <td> 最大 2 個の相関関係 </td> 
   <td> 制限なし </td> 
   <td> 最大 2 個の相関関係 </td> 
   <td colname="col06"> 無制限に分類が可能（セグメントによる分類） </td> 
   <td colname="col6"> 制限なし </td> 
  </tr> 
  <tr> 
   <td> <b>セグメントの比較</b> </td> 
   <td> 制限なし </td> 
   <td> 最大 2 個のセグメント </td> 
   <td> 制限なし </td> 
   <td> 制限なし（データリクエストスタッキング） </td> 
   <td colname="col06"> 1 個のセグメントの呼び出しの後におこなわれる場合です。複数のセグメント（スタック）をサポート </td> 
   <td colname="col6"> 制限なし </td> 
  </tr> 
  <tr> 
   <td> <b>行の出力制限</b> </td> 
   <td> 400 </td> 
   <td> 200 </td> 
   <td> 50,000 </td> 
   <td> 50,000 </td> 
   <td colname="col06"> 制限なし </td> 
   <td colname="col6"> カスタマイズ可能 </td> 
  </tr> 
  <tr> 
   <td> <b>ユニーク値の制限（eVar／prop レポート内）</b> </td> 
   <td> 50 万～200 万 </td> 
   <td> 50 万～200 万 </td> 
   <td> 50 万～200 万 </td> 
   <td> 50 万～200 万 </td> 
   <td colname="col06"> 制限なし </td> 
   <td colname="col6"> カスタマイズ可能 </td> 
  </tr> 
  <tr> 
   <td> <b>ファネル／パス</b> </td> 
   <td> ○ <p> </p> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html"> フォールアウト </a> <p> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html"> フロー </a> </p> </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/reports.html">○</a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-reports-paths.html">○</a> </td> 
   <td> ○ </td> 
   <td colname="col06"> × </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>高度なカスタマージャーニー分析</b> </td> 
   <td> 今後リリース予定 </td> 
   <td> × </td> 
   <td> ○ </td> 
   <td> × </td> 
   <td colname="col06"> × </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>コホート分析</b> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html">○</a> </td> 
   <td> × </td> 
   <td> × </td> 
   <td> × </td> 
   <td colname="col06"> × </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>高度なアトリビューション</b> </td> 
   <td> 現時点で制限あり - 最初／最後／線形 </td> 
   <td> 制限あり - 最初／最後／線形 </td> 
   <td> 制限あり - 最初／最後／線形 </td> 
   <td> 制限あり - 最初／最後／線形 </td> 
   <td colname="col06"> 制限あり - 最初／最後／線形 </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>ビジュアライゼーションの拡張オプション</b> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/analysis-workspace-features.translate.html">○</a> </td> 
   <td> × </td> 
   <td> ○ </td> 
   <td> ○ </td> 
   <td colname="col06"> × </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>レイアウトのカスタマイズ</b> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/analysis-workspace-features.translate.html">○</a> </td> 
   <td> ○ - <a href="https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/server-call-usage-dashboard.html">ダッシュボード</a> </td> 
   <td> × </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/configure-the-custom-layout.html">○</a> </td> 
   <td colname="col06"> <p> 分類または指標による結果の並べ替え </p> </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>プロジェクトのキュレーション（非アナリストを対象とする簡潔なレポート）</b> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html">○</a> </td> 
   <td> × </td> 
   <td> × </td> 
   <td> ○ </td> 
   <td colname="col06"> × </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>プロジェクトの共有</b> </td> 
   <td> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/curate-share/curate.html">○</a>（すべて／任意のユーザー） </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html">○</a>（すべて／任意のユーザー） </td> 
   <td> Ad Hoc Analysis ユーザーのみ </td> 
   <td> ○（すべて／任意のユーザー） </td> 
   <td colname="col06"> × </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>レポート配信のスケジュール設定</b> </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html">○</a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html">○</a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-schedule.html">○</a> </td> 
   <td> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/t-schedule-a-data-request.html">○</a> </td> 
   <td colname="col06"> ○ </td> 
   <td colname="col6"> ○ </td> 
  </tr> 
  <tr> 
   <td> <b>必要システム構成</b> </td> 
   <td> <p>ブラウザー </p> <p> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/server-side-forwarding/ssf-requirements.html"> さらに詳しく... </a> </p> </td> 
   <td> <p>ブラウザー </p> <p> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/server-side-forwarding/ssf-requirements.html"> さらに詳しく... </a> </p> </td> 
   <td> <p>Java </p> <p> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-getting-started.html"> さらに詳しく... </a> </p> </td> 
   <td> <p>Windows、MS Excel </p> <p> <a href="https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/system-requirements.html"> さらに詳しく... </a> </p> </td> 
   <td colname="col06"> ブラウザー、<span class="filepath">.csv</span> ファイルを開くことのできるプログラム（MS Excel など）。Tableau 形式のファイルを生成可能 </td> 
   <td colname="col6"> Windows 64 ビット版、OpenGL 3.2 対応のグラフィックアダプター（<u><a href="https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html">詳細情報...</a></u>） </td> 
  </tr> 
 </tbody> 
</table>

