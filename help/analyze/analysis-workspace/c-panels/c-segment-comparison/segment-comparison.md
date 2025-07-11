---
title: セグメント比較パネルの概要
description: セグメント比較パネルを使用して、Analysis Workspaceのセグメントを比較する方法を説明します。
keywords: Analysis Workspace;Segment IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 76%

---

# セグメント比較パネルの概要 {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="セグメント比較"
>abstract="すべてのデータポイントで 2 つのセグメントをすばやく比較し、関連性の高い差異を自動的に見つけます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="セグメント比較パネル"
>abstract="すべてのデータポイントで 2 つのセグメントをすばやく比較し、関連性の高い差異を自動的に見つけます。<br/><br/>**パラメーター&#x200B;**<br/>**セグメントを追加**：分析する最初のセグメント。<br/>**比較対象**：比較対象となる 2 番目のセグメントで、*その他すべて*（最初のセグメントの逆）が自動的に入力されます。必要に応じて、*その他すべて*&#x200B;を別のセグメントに置き換えることができます。<br/>**詳細設定**：セグメント比較で分析するコンポーネントを除外する機能。"
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_この記事では、_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** のセグメント比較パネルについて説明します。_<br/>__![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** には同等のパネルはありません。_

>[!ENDSHADEBOX]

セグメント比較パネルでは、無数のセグメント間の統計的に最も有意な差異を見つけることができます。 この機能は、アクセス権を持つすべてのディメンションと指標の自動分析を繰り返し実行します。比較では、会社の KPI を推進しているオーディエンスセグメントの主な特性が自動的に明らかになり、セグメントの重複がどれくらい見えるかを確認できます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [セグメント比較](https://video.tv.adobe.com/v/37627?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]



## 使用

**[!UICONTROL アトリビューション]**&#x200B;パネルを使用するには：

1. **[!UICONTROL アトリビューション]**&#x200B;パネルを作成します。パネルの作成方法について詳しくは、[パネルの作成](../panels.md#create-a-panel)を参照してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。



### パネル入力

次の入力設定を使用して、[!UICONTROL セグメント比較]パネルを設定できます。

![セグメント比較入力パネル](assets/segment-comparison-input.png)

| 入力 | 説明 |
| --- | --- |
| **[!UICONTROL セグメントを追加]** | 比較するディメンションを選択します。 |
| **[!UICONTROL 比較対象]** | 最初に選択したセグメントの比較に使用するディメンションを選択します。 特定のセグメントを選択しない場合、デフォルトのセグメントである「**[!UICONTROL 他の全員]**」が使用されます。 |
| **[!UICONTROL 詳細設定を表示／非表示]** | **[!UICONTROL 除外されたコンポーネント]**&#x200B;を設定するには「**[!UICONTROL 詳細設定を表示]**」を選択し、**[!UICONTROL 除外されたコンポーネント]**&#x200B;を非表示にするには「**[!UICONTROL 詳細設定を非表示]**」を選択します。 |
| **[!UICONTROL 除外されたコンポーネント]** | 除外する&#x200B;**[!UICONTROL ディメンション]**、**[!UICONTROL 指標]**&#x200B;または&#x200B;**[!UICONTROL セグメント]**&#x200B;などを指定できるコンポーネント。<br><ul><li>1 つ以上のディメンション、指標またはセグメントをコンテナから&#x200B;**[!UICONTROL 除外されたコンポーネント]**&#x200B;コンテナにドラッグ＆ドロップします。</li><li>コンポーネントを削除するには、タイプ（**[!UICONTROL ディメンション]**、**[!UICONTROL 指標]**&#x200B;または&#x200B;**[!UICONTROL セグメント]**）を選択し、![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択してコンポーネントを削除します。すべてのコンポーネントを削除するには、「**[!UICONTROL すべてクリア]**」を選択します。</li><li>現在のディメンション、指標、セグメントの選択をデフォルトとして設定するには、「**[!UICONTROL デフォルトとして設定]**」を選択します。</li></ul> |

「**[!UICONTROL 作成]**」を選択して、パネルを作成します。

### パネル出力

Adobe Analyticsが 2 つの目的のセグメントの分析を完了すると、出力パネルに複数のビジュアライゼーションを通じて結果が表示されます。

![パネル出力のセグメント比較](assets/segment-comparison-output.png)

| ビジュアライゼーション | 説明 |
|---|---|
| **[!UICONTROL サイズと重複]** | 選択した各セグメントの比較サイズと、これらが互いにどの程度重複しているかを[ベン図](/help/analyze/analysis-workspace/visualizations/venn.md)ビジュアライゼーションで示します。 |
| **[!UICONTROL 最初のセグメントのユニーク訪問者]** | 最初のセグメントのユニーク訪問者を表示する [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション（単一ページ訪問数の例の場合） |
| **[!UICONTROL 2 番目のセグメントのユニーク訪問者]** | 2 番目のセグメントのユニーク訪問者を示す [ 概要番号 ](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) ビジュアライゼーション（初回訪問の例の場合） |
| **[!UICONTROL セグメントに対する上位の指標]** | 選択したセグメントに対する上位の指標を示す[フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 |
| **[!UICONTROL セグメント別の経時的な指標]** | 選択したセグメントに対する経時的な指標を示す[折れ線グラフ](/help/analyze/analysis-workspace/visualizations/line.md)ビジュアライゼーション。 |
| **[!UICONTROL セグメントに対する上位のディメンション項目]** | 選択したセグメントに対する混合ディメンション項目を示す[フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 |
| **[!UICONTROL セグメント別のディメンション項目]** | セグメント別にディメンション項目を示す[横棒グラフ](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)ビジュアライゼーション。 |
| **[!UICONTROL セグメントに対する上位のセグメント]** | セグメントに対する上位のセグメントを示す[フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 |
| **[!UICONTROL セグメントの重複]** | セグメントの重複を示す[ベン図](/help/analyze/analysis-workspace/visualizations/venn.md)ビジュアライゼーション。 |

パネルを再設定および再作成するには、![編集](/help/assets/icons/Edit.svg) を使用します。


<!--
#### Size and overlap

Illustrates the comparative sizes of each selected segment and how much they overlap with each other using a venn diagram. You can hover over the visual to see how many visitors were in each overlapping or non-overlapping section. You can also right click on the overlap to create a brand new segment for further analysis. If the two segments are mutually exclusive, no overlap is shown between the two circles (typically seen with segments using a hit container).

![Size and overlap](assets/size-overlap.png)

#### Population summaries

To the right of the Size and Overlap visualization, the total unique visitor count in each segment and overlap is shown.

![Population summaries](assets/population_summaries.png)

#### Top metrics

Displays the most statistically significant metrics between the two segments. Each row in this table represents a differentiating metric, ranked by how different it is between each segment. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific metric is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific metric. If a metric is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Metrics added to this table after the segment comparison has finished do not receive a Difference Score.

![Top metrics](assets/top-metrics.png)

#### Metric over time by segment

To the right of the metrics table is a linked visualization. You can click a line item in the table on the left, and this visualization updates to show that metric trended over time.

![Top metrics line](assets/linked-viz.png)

#### Top dimensions

Shows the most statistically significant dimension items across all of your dimensions. Each row shows the percentage of each segment exhibiting this dimension item. For example, this table might reveal that 100% of visitors in 'Segment A' had the dimension item 'Browser Type: Google', whereas only 19.6% of 'Segment B' had this dimension item. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific dimension item is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific dimension item. If a dimension item is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Dimension items added to this table after the segment comparison has finished do not receive a Difference Score.

![Top dimensions](assets/top-dimension-item1.png)

#### Dimension items by segment

To the right of the dimensions table is a linked bar chart visualization. It shows all displayed dimension items in a bar chart. Clicking a line item in the table on the left updates the visualization on the right.

![Top dimensions bar chart](assets/top-dimension-item.png)

#### Top segments

Shows which other segments (other than the two segments selected for comparison) have statistically significant overlap. For example, this table can show that a third segment, 'Repeat Visitors', overlaps highly with 'Segment A' but does not overlap with 'Segment B'. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific segment is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific segment. If a segment is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Segments added to this table after the segment comparison has finished do not receive a Difference Score.

![Top segments](assets/top-segments.png)

#### Segment overlap

To the right of the segments table is a linked venn diagram visualization. It shows the most statistically significant segment applied to your compared segments. For example, 'Segment A' + 'Statistically significant segment' vs. 'Segment B' + 'Statistically significant segment'. Clicking a segment line item in the table on the left updates the venn diagram on the right.

![Top segments venn diagram](assets/segment-overlap.png)

-->
