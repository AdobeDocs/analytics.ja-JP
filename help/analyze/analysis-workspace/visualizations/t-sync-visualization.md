---
description: ビジュアライゼーションをフリーフォームテーブルデータソースにリンクする方法を説明します。
keywords: Analysis Workspace;ビジュアライゼーションとデータソースの同期
title: Analysis Workspaceでのビジュアライゼーションデータソースの管理
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
TQID: https://experienceleague.adobe.com/ZteQfWHbl29KbcI-OUvvjEXgKytSIuR8l5R40zWQ-Rk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 19e31fec475abe3805e2637949dc86171123c210
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 18%
---
# データソースの管理 {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="選択をロック"
>abstract="この設定を有効にすると、ビジュアライゼーションがデータソースで選択した位置または選択した項目にロックされます。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="テーブルの表示"
>abstract="**[!UICONTROL テーブルを表示]**&#x200B;を選択すると、元のデータソースとは別に、現在のビジュアライゼーション用に新しいデータソースが生成されます。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="テーブルの表示"
>abstract="「**[!UICONTROL テーブルを表示]**」を選択して、元のデータソースとは別に、現在のビジュアライゼーション用の新しいデータソースを生成します。"

Analysis Workspaceの各ビジュアライゼーションは、データソース（通常はフリーフォームテーブル）に基づいています。 ビジュアライゼーションを同期すると、どのフリーフォームテーブルまたはデータソースがビジュアライゼーションに対応するか、ビジュアライゼーションがそのテーブル内の特定の行にロックされたままであるかどうかを制御できます。

>[!TIP]
>
>ビジュアライゼーションのタイトルの横の ![StatusOrange](/help/assets/icons/StatusOrange.svg) の色で、どのビジュアライゼーションが関連しているかがわかります。 色が一致していると、ビジュアライゼーションが同じデータソースに基づいていることを意味します。
>

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

## データソースの設定 {#configure}

1. Analysis Workspaceで、設定するデータソースまたはロック設定のビジュアライゼーションに移動します。

1. ビジュアライゼーションにカーソルを合わせ、**[!UICONTROL 設定]** アイコン ![設定](/help/assets/icons/Setting.svg)を選択します。

1. 「**[!UICONTROL データソース]**」タブを選択します。

   ![&#x200B; データソース、リンクされたビジュアライゼーション、およびロック選択設定を示す「データソース」タブ。](assets/lock-selection.png)

1. 次のいずれかの設定を行います。

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL データソース]** | ビジュアライゼーションの基となるデータソースを選択します。 |
   | **[!UICONTROL リンクされたビジュアライゼーション]** | データソース（フリーフォームテーブル）にリンクされているすべてのビジュアライゼーションを一覧表示します。 |
   | **[!UICONTROL データソースを表示]** | ビジュアライゼーションに対応するデータソース（フリーフォームテーブル）を表示または非表示にします。 |
   | **[!UICONTROL 選択範囲をロック]** | データソースで現在選択されている行にビジュアライゼーションをロックしてから、**[!UICONTROL 選択した位置]**&#x200B;または&#x200B;**[!UICONTROL 選択した項目]**&#x200B;を選択します。 [選択範囲をロック &#x200B;](#lock-selection)を参照してください。 |

## 選択をロック {#lock-selection}

選択範囲をロックすると、テーブルが変更されたときでも、データソース内で選択した行に焦点を当てたビジュアライゼーションが維持されます。 例えば、並べ替えやフィルタリング、日付範囲の変更、セグメントの適用などを行うと、テーブルが変更されます。 ロックされたビジュアライゼーションには、タイトルの横に![LockClosed](/help/assets/icons/LockClosed.svg)が表示されます。

データソース内のセグメント、ディメンションまたは指標が変更され、ロックされたデータが表示されなくなった場合は、**[!UICONTROL テーブルを表示]**&#x200B;を選択して、元のデータソースとは別に、ビジュアライゼーション用の新しいデータソースを生成します。

選択範囲をロックする場合は、次のいずれかのオプションを選択します。

| オプション | 説明 |
| --- | --- |
| **[!UICONTROL 選択した職位]** | ビジュアライゼーションを、データソースで選択された行の&#x200B;**位置**&#x200B;にロックします。 それらの位置は、項目が変更されても、引き続き視覚化されます。 例えば、どのキャンペーンであるかに関係なく、データソースの上位5つのキャンペーン名を常に表示するには、このオプションを選択します。<br><br>分類の行をロックし、それらの行がテーブルに存在しなくなった場合、ビジュアライゼーションは表示されません。 もう一度表示するには、テーブル（日付範囲、セグメント、フィルターなど）を更新するか、ロック選択を更新します。 |
| **[!UICONTROL 選択した項目]** | データソースで選択された特定の&#x200B;**項目**&#x200B;にビジュアライゼーションをロックします。 テーブル内のランキングが変更されても、それらの項目は引き続き可視化されます。 例えば、ランクに関係なく、常に同じ5つのキャンペーン名を表示するには、このオプションを選択します。 |
