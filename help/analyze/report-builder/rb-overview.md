---
title: Report Builder の概要
description: Report Builder の機能について説明します
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 100%

---

# Report Builder の概要

当初は Customer Journey Analytics でのみ使用可能であった新しい Javascript Report Builder アドインが、Adobe Analytics にも導入されるようになりました。この新しいバージョンには、次のようないくつかの利点があります。

- データブロックの柔軟性の向上など、データブロックの作成と管理のワークフローが改善され、Excel でより迅速かつ簡単にインサイトの検索が可能
- クロスプラットフォーム：PC、Mac、Excel Online がサポートされるようになったので、Report Builder を使用するための VM へのログインが不要
- API 2.0 のアップグレードにより、データブロックが返されるまでの待ち時間が短縮
- 速度の向上

レガシー Report Builder ツール使用のユーザーは、新しい Report Builder に[レガシーワークブックを変換](/help/analyze/report-builder/convert-workbooks.md)できます。

Report Builder を使用すると、Adobe Analytics データを使用したカスタムレポートの作成、編集、更新を簡単に行うことができます。Report Builder のシンプルで柔軟なドラッグ＆ドロップ UI を使用すると、Adobe Analytics データから複雑なデータクエリやカスタムレポートをすべて Excel 内で作成できます。

Report Builder では、次のことが行えます。

- 既存のワークシートセルを参照して、適切な行の順序、日付範囲またはフィルターを取得
- カレンダー、セル参照または日付計算を使用したカスタム日付を作成
- 慣れ親しんだ Excel 書式設定ツールを使用してテーブルおよびビジュアライゼーションをデザイン

## レガシー Report Builder と新しい Report Builder の並列使用

両方のバージョンの Report Builder を引き続き使用できますが、次の注意事項があります。

- 同じファイルで両方の Report Builder バージョンを同時に使用しないでください。相互に排他的です。
- レガシーワークブックではレガシー Report Builder を、新しいワークブックでは新しい Report Builder を引き続き使用できます。
- また、新しい Report Builder 形式に自動的に[レガシーワークブックを変換](/help/analyze/report-builder/convert-workbooks.md)できます。これを行う前に、ファイルを複製して名前を変更します。

## 新しい Report Builder でサポートされていないレガシー Report Builder 機能

レガシー Report Builder の機能と新しい Report Builder アドインの機能を比較すると、一部のレガシー機能は使用できなくなっています。

- リアルタイムリクエスト

- パス／フォールアウトレポート

- 予定レポートの FTP オプション

- 訪問者指標。レポート結果が完全に一致しない場合でも、`visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly` および `visitorsyearly` の指標はすべて「ユニーク訪問者」に変換されます。これは、`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` および `mobilevisitorsyearly` にも適用されます。

## 一般的なユースケース

- **データ抽出**：Adobe Report Builder を使用すると、Adobe Analytics から Excel にデータを抽出できます。カスタムレポートやクエリを作成して、分析に関連する特定のデータポイントを取得できます。

- **カスタムレポート**：Excel で、特定のレポートのニーズに合わせて、カスタムレポートをデザインしたり、形式を設定したりできます。これは、様々な関係者に応じてレポートを調整する場合に特に便利です。

- **アドホック分析**：ユーザーは時間のかかるレポート作成プロセスを経ずに、特定の質問に回答したり、データのトレンドを調べたりするアドホックレポートを迅速に生成できます。

- **ダッシュボーディング**：CJA から抽出したデータを使用して、Excel ベースのダッシュボードと主要業績評価指標（KPI）の概要を視覚化することができます。

- **インサイトの共有**：CJA に直接アクセスできないチームメンバーや関係者と、Excel のレポートやインサイトを共有できます。

## 概要ビデオ

>[!IMPORTANT]
>
>この概要ビデオでは、Customer Journey Analytics の Report Builder ユーザーインターフェイスについて説明します。一部のユーザーインターフェイスと用語が異なります。それ以外の場合は、ユーザーエクスペリエンスは同じです。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Report Builder の概要](https://video.tv.adobe.com/v/3452581?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

Report Builder は、[Microsoft Store](https://appsource.microsoft.com/ja-jp/product/office/WA200003101?tab=Overview) からダウンロードできます。
