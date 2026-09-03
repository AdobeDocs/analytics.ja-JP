---
description: Analysis Workspaceでのセグメントの使用方法を説明します。
title: セグメントを使用
role: User
exl-id: 870026e2-a3a3-4d87-a6c2-6189098d3676
TQID: https://experienceleague.adobe.com/IomFGqUqZ9VBamW0bRF-X2w0SdlUHvyygKOS4HSuhnM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 1%

---

# セグメントの使用

Analysis Workspace全体でセグメントを使用するには、コンポーネントパネルの&#x200B;**[!UICONTROL セグメント]**&#x200B;から1つ以上のセグメントをドラッグして、次の場所にドロップします。

* Analysis Workspaceの[&#x200B; パネル &#x200B;](/help/analyze/analysis-workspace/c-panels/panels.md)が、パネル内のすべてのビジュアライゼーションをセグメント化します。
* ディメンションを置き換えるAnalysis Workspaceの[&#x200B; フリーフォームテーブル &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)のヘッダー行。
* Analysis Workspaceの[&#x200B; フリーフォームテーブル &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)の行で、分類を開始します。
* Analysis Workspaceの[自由形式テーブル &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)の列で、列を追加または置換するか、フィルターを開始します。
* ビジュアライゼーション用の設定パネルまたはセグメントをドロップできるパネル。 例えば、[&#x200B; セグメント比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) パネルや[主要指標](/help/analyze/analysis-workspace/visualizations/key-metric.md)の概要ビジュアライゼーションで
* セグメント定義にセグメントを含めるには、セグメントの[定義ビルダー](/help/components/segmentation/segmentation-workflow/seg-build.md#definition-builder)が必要です。
* 計算指標[&#128279;](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md#definition-builder)の定義ビルダー。計算指標の定義にセグメントを含めます。

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
