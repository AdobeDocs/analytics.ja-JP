---
title: Report Builder の概要
description: Report Builderの機能の詳細。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
TQID: https://experienceleague.adobe.com/4BaqA2FPfve4sF2K-Tpxd0hcbVlAWw2QeVhl4xxeb9s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 514
ht-degree: 73%

---

# Report Builder の概要

Report Builder を使用すると、Adobe Analytics データを使用したカスタムレポートの作成、編集、更新を簡単に行うことができます。 Report Builder のシンプルで柔軟なドラッグ＆ドロップ UI を使用すると、Adobe Analytics データから複雑なデータクエリやカスタムレポートをすべて Excel 内で作成できます。

Adobe Analytics版Report Builderでは、次のことが可能です。

- 既存のワークシートセルを参照し、適切な行の順序、日付範囲、セグメントを取得。
- カレンダー、セル参照、日付計算を使用してカスタム日付を作成。
- 使い慣れたExcelの書式設定ツールを使用して、テーブルおよびビジュアライゼーションをデザインします。

Report Builder for Adobe Analyticsは、Microsoft Excel用のアドインです。 アドインは、次のプラットフォームで使用できます。

- macOS
- Windows
- Web ブラウザー


## レガシー Report Builder

このReport Builderは、[従来のReport Builder アドイン &#x200B;](/help/analyze/legacy-report-builder/home.md)に取って代わるもので、次のようなメリットがあります。

- データブロックの柔軟性の向上など、データブロックの作成と管理のワークフローが改善され、Excel でより迅速かつ簡単にインサイトの検索が可能
- クロスプラットフォーム：PC、Mac、Excel Online がサポートされるようになったので、Report Builder を使用するための VM へのログインが不要
- API 2.0 のアップグレードにより、データブロックが返されるまでの待ち時間が短縮
- 速度の向上

レガシー Report Builder ツール使用のユーザーは、新しい Report Builder に[レガシーワークブックを変換](/help/analyze/report-builder/convert-workbooks.md)できます。


### 両方のバージョンを並べて使用する

両方のバージョンの Report Builder を引き続き使用できますが、次の注意事項があります。

- 同じファイルで両方の Report Builder バージョンを同時に使用しないでください。 相互に排他的です。
- レガシーワークブックではレガシー Report Builder を、新しいワークブックでは新しい Report Builder を引き続き使用できます。
- また、新しい Report Builder 形式に自動的に[レガシーワークブックを変換](/help/analyze/report-builder/convert-workbooks.md)できます。 これを行う前に、ファイルを複製して名前を変更します。

### 従来のReport Builder機能はサポートされていません

このReport Builderでは、従来のReport Builderの一部[機能がサポートされていません](convert-workbooks.md#legacy-report-builder-features-not-supported)。


## 一般的なユースケース

- **データ抽出**：Adobe Report Builder を使用すると、Adobe Analytics から Excel にデータを抽出できます。 カスタムレポートやクエリを作成して、分析に関連する特定のデータポイントを取得できます。

- **カスタムレポート**：Excel で、特定のレポートのニーズに合わせて、カスタムレポートをデザインしたり、形式を設定したりできます。 これは、様々な関係者に応じてレポートを調整する場合に特に便利です。

- **アドホック分析**：ユーザーは時間のかかるレポート作成プロセスを経ずに、特定の質問に回答したり、データのトレンドを調べたりするアドホックレポートを迅速に生成できます。

- **ダッシュボーディング**：CJA から抽出したデータを使用して、Excel ベースのダッシュボードと主要業績評価指標（KPI）の概要を視覚化することができます。

- **インサイトの共有**：CJA に直接アクセスできないチームメンバーや関係者と、Excel のレポートやインサイトを共有できます。

## 概要ビデオ

>[!IMPORTANT]
>
>この概要ビデオでは、Customer Journey Analytics の Report Builder ユーザーインターフェイスについて説明します。 Adobe AnalyticsでReport Builderを使用する場合、ユーザーインターフェイスと用語の一部が異なります。 それ以外の場合は、ユーザーエクスペリエンスは同じです。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Report Builder の概要](https://video.tv.adobe.com/v/337569?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

Report Builderは、[Adobe Analytics Store](https://appsource.microsoft.com/ja-jp/product/office/WA200003101?tab=Overview)からMicrosoftをダウンロードできます。
