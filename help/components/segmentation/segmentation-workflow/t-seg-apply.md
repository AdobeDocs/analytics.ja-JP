---
description: Analysis Workspaceでセグメントを使用する方法について説明します。
title: セグメントの使用
role: User
exl-id: 870026e2-a3a3-4d87-a6c2-6189098d3676
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 1%

---

# セグメントの使用

Analysis Workspace全体でセグメントを使用するには、コンポーネントパネルの **[!UICONTROL セグメント]** から 1 つ以上のセグメントをドラッグして、次の場所にドロップします。

* パネル内のすべてのビジュアライゼーションをセグメント化するAnalysis Workspaceの [ パネル ](/help/analyze/analysis-workspace/c-panels/panels.md)。
* ディメンションを置き換えるAnalysis Workspaceの [ フリーフォームテーブル ](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) のヘッダー行
* Analysis Workspaceの [ フリーフォームテーブル ](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) の行で、分類を開始します。
* Analysis Workspaceの [ フリーフォームテーブル ](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) の列で、列の追加や置換、フィルターの開始を行います。
* ビジュアライゼーションの設定パネルまたはセグメントをドロップできるパネル。 例えば、[ セグメント比較 ](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) パネルまたは [ 主要指標 ](/help/analyze/analysis-workspace/visualizations/key-metric.md) 概要ビジュアライゼーションで次の操作を行います
* セグメント定義にセグメントを含めるために、[ セグメントの定義ビルダー ](/help/components/segmentation/segmentation-workflow/seg-build.md#definition-builder) を選択します。
* 計算指標の定義にセグメントを含めるように、[ 計算指標の定義ビルダー ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#definition-builder) を設定します。

<!--
How to apply one or more segments to a report from the segment rail.

1. Bring up the report to which you want to apply a segment, for example the [!UICONTROL Pages Report].
1. Click **[!UICONTROL Show Segments]** above the report. The segment rail opens.

   ![](assets/segment_rail.png)

1. Mark the checkbox next to one or more of the segments or **[!UICONTROL Search Segments]** to find the right segment.

   >[!NOTE]
   >
   >You can apply more than one segment to a report (this is called segment stacking). When multiple segments are applied, the criteria in each segment is combined using an 'and' operator and then applied. There is no limit to how many segments you can stack.

   >[!NOTE]
   >
   >Clicking the Information icon (i) next to the segment name lets you preview the key metrics to see whether you have a valid segment and how broad the segment is.

1. You can filter by report suite by selecting the **[!UICONTROL (Only) `<report suite name>`]** check box. This will show only those segments that were last saved in that report suite.
1. Click **[!UICONTROL Apply Segment]** and the report will refresh. The segment or segments that are applied now display at the top of the report:

   ![](assets/applied_segments.png)

-->
