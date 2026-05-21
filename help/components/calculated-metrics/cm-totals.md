---
title: 計算指標の合計
description: Analysis Workspaceの計算指標の合計について説明します
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
TQID: https://experienceleague.adobe.com/3UJF1Hl3nLqjYAiQuvcE4Jpq26MaTgeba5BmnVfvEps
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: dcae653e-62c6-4cc8-84e6-ee110b848296id: e318d41c-1d01-4c1e-9b18-1f61d435ceeeid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 149
ht-degree: 94%

---

# 計算指標の合計

Analysis Workspace でデータを表示すると、ほとんどの場合、計算指標の合計が表示されます。 レポートの行の形式（小数や通貨など）が混在している場合など、合計を指定できないことがあります。

合計が表示されている場合は多くの場合、サーバー側で計算され、訪問回数や訪問者数などの指標の重複を排除します。 状況によっては、テーブルの行全体を合計して、クライアント側で計算指標が生成されることがあります。つまり、合計では、訪問回数や訪問者数などの指標の重複が排除されません。 これは次のように発生します。

* フリーフォームテーブルで、[静的な行](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)が使用され、「**[!UICONTROL 現在の行の合計として表示]**」オプション（デフォルト）が選択されている場合。
* [ドーナツビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/donut.md)では、数値の合計は 100％になります。

Analysis Workspace での合計の詳細については、[Workspace の合計](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total)を参照してください。
