---
description: 基本的な Report Builder データリクエストを作成する手順です。
title: データリクエストの作成
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Report Builder データリクエストの作成

基本的なデータリクエストを作成する手順です。

1. In Excel, click **[!UICONTROL Create]**.
1. ウィンドウ [!UICONTROL Request Wizard: Step 1] で、レポートスイート [を選択します](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。
1. （オプション）リクエストに適用するセグメントを選択します。1 つまたは複数のセグメントを選択したら、リストのトップに移動します。

   Report Builder では、Adobe Analytics と同様の方法でセグメントを使用します。[Analytics セグメントガイド](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/seg-home.html)を参照してください。1.（オプション）配布に使用する[発行リスト](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)を選択します。
1. 「[レポートタイプ](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)」を選択します。
1. 「[日付範囲](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)」を指定してレポートの「[精度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)」をクリックします。
1. クリック **[!UICONTROL Next]**.
1. [レイアウト - リクエストウィザード：ステップ 2](/help/analyze/report-builder/layout/layout.md) ウィンドウで、レイアウトを選択します。

   | 要素 | 説明 |
   |---|---|
   | ピボットレイアウト | Excel の標準的な表と同様に、レイアウトの行、列および指標グリッドを指定できます。このレイアウトを使用すると、オリジナルのリクエストをクロス集計できます。 |
   | カスタムレイアウト | Provides most of the functionality of the [!UICONTROL Pivot Layout] but lets you choose where each item in the grid should be located in the spreadsheet. このレイアウトは、以前のバージョンで提供されていたもので、柔軟な指定が可能です。 |

1. On the [!UICONTROL Metrics] tab, double-click (or drag) metrics in the tree to add them to the [!UICONTROL Metrics] grid.
1. On the [!UICONTROL Dimensions] tab, double-click (or drag) dimensions to the [!UICONTROL Row Labels] grid.

   ステップ 2 で使用可能な[ディメンション](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html)は、ステップ 1 で選択したベースレポート、およびレポートスイートの設定によって異なります。The dimensions are items that correlate, sub-relate, or are a classification of the original report type metric you selected on the [!UICONTROL Request Wizard: Step 1] window. ディメンションをクロス集計するには、ステップ 2 で複数のディメンションを追加します。

   詳しくは、[指標およびディメンションの追加](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)を参照してください。
