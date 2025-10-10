---
description: フリーフォームテーブルまたはデータソースを対応するビジュアライゼーションに同期する方法を説明します。
keywords: Analysis Workspace;ビジュアライゼーションのデータソースとの同期
title: データソースの管理
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 89%

---

# データソースの管理 {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="選択をロック"
>abstract="この設定を有効にすると、ビジュアライゼーションがデータソースで選択した位置または選択した項目にロックされます。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="テーブルの表示"
>abstract="「**[!UICONTROL テーブルを表示]**」を選択すると、元のデータソースとは別に、現在のビジュアライゼーション用の新しいデータソースが生成されます。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="テーブルの表示"
>abstract="「**[!UICONTROL テーブルを表示]**」を選択して、元のデータソースとは別に、現在のビジュアライゼーション用の新しいデータソースを生成します。"


ビジュアライゼーションを同期すると、ビジュアライゼーションに対応するフリーフォームテーブルまたはデータソースを制御できます。


>[!TIP]
>
>ビジュアライゼーションのタイトルの横の ![StatusOrange](/help/assets/icons/StatusOrange.svg) の色で、どのビジュアライゼーションが関連しているかがわかります。色が一致していると、ビジュアライゼーションが同じデータソースに基づいていることを意味します。
>

データソースの表示/非表示を切り替えることができます。選択した位置または選択した項目に対して選択をロックすることもできます。これらの設定は、新しいデータが入ってきた際にどのようにビジュアライゼーションを変更するか（または変更しないか）を決定します。

![次の節で説明するオプションを示したデータソースオプションダイアログ](assets/lock-selection.png)

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/328260?quality=12&learn=on&captions=jpn){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

| オプション | 説明 |
|--- |--- |
| **[!UICONTROL データソース]** | ドロップダウンメニューから、ビジュアライゼーションの基になるデータソースを選択します。 |
| **[!UICONTROL リンクされたビジュアライゼーション]** | すべてのリンクされたビジュアライゼーションを一覧表示します。データソース（フリーフォームテーブル）に適用されます。 |
| **[!UICONTROL データソースを表示]** | ビジュアライゼーションに対応するデータソース（フリーフォームテーブル）の表示と非表示を切り替えることができます。 |
| **[!UICONTROL 選択をロック]** | このオプション選択すると、ビジュアライゼーション ![LockClosed](/help/assets/icons/LockClosed.svg) を、対応するデータテーブルで現在選択されているデータにロックできます。チェックボックスをオンにすると、次のいずれかを選択できます。  <ul><li>**選択された位置**：ビジュアライゼーションは、対応するデータテーブルで選択された&#x200B;**位置**&#x200B;でロックされます。これらの位置の特定の項目が変更された場合（例えば、並べ替えやフィルタリングが原因）でも、これらの位置は引き続き視覚化されます。例えば、このビジュアライゼーションのデータソースにリストされた上位 5 つのキャンペーン名を常に表示する場合は、このオプションを選択します。どのキャンペーン名が表示されても問題ありません。</li> <li>**選択された項目**：対応するデータテーブルで現在選択されている特定の&#x200B;**項目**&#x200B;に対して、ビジュアライゼーションがロックされます。これらの項目は、テーブル内の項目間のランキングが変更された場合でも、引き続き視覚化されます。例えば、このビジュアライゼーションのデータソースにリストされた同じ 5 つの特定のキャンペーン名を常に表示する場合は、このオプションを選択します。キャンペーン名の順位がどうであろうと関係ありません。</li></ul>接続されたデータテーブルに表示されなくなったデータに対してビジュアライゼーションがロックされている場合は、新しいテーブルを生成できます。「**[!UICONTROL テーブルを表示]**」を選択すると、元のデータソースとは別に、現在のビジュアライゼーション用の新しいデータソースが生成されます。 |
