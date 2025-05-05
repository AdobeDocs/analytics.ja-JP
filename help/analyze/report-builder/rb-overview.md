---
title: Report Builderの概要
description: Report Builderの機能について説明します
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 29%

---

# Report Builderの概要

当初はCustomer Journey Analyticsでのみ使用できた新しい Javascript Report Builder アドインも、Adobe Analyticsで導入されるようになりました。 この新しいバージョンには、次のようないくつかの利点があります。

- データブロックの柔軟性の向上など、データブロックの作成と管理のワークフローが改善され、Excel でのインサイトをより迅速かつ簡単に見つけることができます
- クロスプラットフォーム：PC、Mac、Excel Online がサポートされるようになり、仮想マシンにログインしてReport Builderを使用する必要がなくなりました
- API 2.0 のアップグレードにより、データブロックが返されるのを待つ時間が短縮されました。
- 速度の向上。

従来のReport Builder ツールを使用すると、新しいReport Builderに [ 従来のワークブックを変換 ](/help/analyze/report-builder/convert-workbooks.md) できます。

Report Builderでは、Adobe Analytics データを使用して、カスタムレポートを簡単に作成、編集、更新できます。 Report Builderのシンプルで柔軟なドラッグ&amp;ドロップ UI を使用すると、Adobe Analytics データから複雑なデータクエリやカスタムレポートをすべて Excel 内で作成できます。

Report Builderを使用すると、次のことができます。

- 既存のワークシートセルを参照して、適切な行の順序、日付範囲またはフィルターを取得
- カレンダー、セル参照または日付計算を使用したカスタム日付を作成
- 慣れ親しんだ Excel 書式設定ツールを使用してテーブルおよびビジュアライゼーションをデザイン

## 従来のReport Builderと新しいReport Builderを並べて使用

両方のバージョンのReport Builderを引き続き使用できますが、その際に次の点に注意してください。

- 同じファイルで両方のReport Builder バージョンを同時に使用しないでください。 それらは相互に排他的です。
- 従来のワークブックでは従来のReport Builderを使用し、新しいワークブックでは新しいReport Builderを使用できます。
- また、従来のワークブックを新しいReport Builder形式に自動的に [ 変換 ](/help/analyze/report-builder/convert-workbooks.md) することもできます。 その前に、ファイルを複製して名前を変更します。

## ニューReport Builderでサポートされていない従来のReport Builder機能

従来のReport Builderの機能と新しいReport Builder アドインを比較すると、一部の従来の機能は使用できなくなりました。

- リアルタイムリクエスト

- パス/フォールアウトレポート

- 予定レポートの FTP オプション

- 訪問者指標。 レポート結果が完全には一致しない場合でも、`visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly` および `visitorsyearly` の指標はすべて「ユニーク訪問者」に変換されます。 これは、`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` および `mobilevisitorsyearly` にも適用されます。

## 一般的なユースケース

- **データ書き出し**: Adobe Report Builderでは、Adobe Analyticsから Excel にデータを書き出すことができます。 カスタムレポートやクエリを作成して、分析に関連する特定のデータポイントを取得できます。

- **カスタムレポート**：Excel で、特定のレポートのニーズに合わせて、カスタムレポートをデザインしたり、形式を設定したりできます。これは、様々な関係者に応じてレポートを調整する場合に特に便利です。

- **アドホック分析**：ユーザーは時間のかかるレポート作成プロセスを経ずに、特定の質問に回答したり、データのトレンドを調べたりするアドホックレポートを迅速に生成できます。

- **ダッシュボーディング**：CJA から抽出したデータを使用して、Excel ベースのダッシュボードと主要業績評価指標（KPI）の概要を視覚化することができます。

- **インサイトの共有**：CJA に直接アクセスできないチームメンバーや関係者と、Excel のレポートやインサイトを共有できます。

## 概要ビデオ

>[!IMPORTANT]
>
>この概要ビデオでは、Customer Journey AnalyticsのReport Builder ユーザーインターフェイスについて説明します。 一部のユーザーインターフェイスと用語は異なります。 それ以外の場合、ユーザーエクスペリエンスは同じです。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Report Builderの概要 ](https://video.tv.adobe.com/v/3452581?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]

Report Builderは [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview) からダウンロードできます。
