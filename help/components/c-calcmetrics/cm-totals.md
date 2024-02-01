---
title: 計算指標の合計
description: Analysis Workspaceでの計算指標の合計について説明します。
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 89%

---

# Analysis Workspaceでの計算指標の合計

Analysis Workspace でデータを表示すると、ほとんどの場合、計算指標の合計が表示されます。レポートの行の形式（小数や通貨など）が混在している場合など、合計を指定できないことがあります。

合計が表示されている場合は多くの場合、サーバー側で計算され、訪問回数や訪問者数などの指標の重複を排除します。状況によっては、テーブルの行全体を合計して、クライアント側で計算指標が生成されることがあります。つまり、合計では、訪問回数や訪問者数などの指標の重複が排除されません。これは次のように発生します。

* フリーフォームテーブルで、[静的な行](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)が使用され、「**[!UICONTROL 現在の行の合計として表示]**」オプション（デフォルト）が選択されている場合。
* [ドーナツビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/donut.md)では、数値の合計は 100％になります。

Analysis Workspace での合計の詳細については、[Workspace の合計](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html#static-row-total)を参照してください。
