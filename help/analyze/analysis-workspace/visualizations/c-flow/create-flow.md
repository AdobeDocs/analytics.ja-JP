---
description: Analysis Workspaceでフロービジュアライゼーションを設定する方法を説明します
title: フロービジュアライゼーションの設定
feature: Visualizations
role: User, Admin
exl-id: c2fdcc96-81ac-4d3b-b255-ff805b6ff0ea
source-git-commit: f7a433e996b234fa46556f4bd40584b474d568c3
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 88%

---

# フロービジュアライゼーションの設定 {#configure-a-flow-visualization}

>[!CONTEXTUALHELP]
>id="workspace_flow_startswith"
>title="次の語句で始まる"
>abstract="このフィールドは、最初のビルドでのみ設定できます。このフィールドを更新するには、「**[!UICONTROL リセット]**」を選択して、新しいフロービジュアライゼーションを作成します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_contains"
>title="次を含む"
>abstract="このフィールドは、最初のビルドでのみ設定できます。このフィールドを更新するには、「**[!UICONTROL リセット]**」を選択して、新しいフロービジュアライゼーションを作成します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_endswith"
>title="次の語句で終わる"
>abstract="このフィールドは、最初のビルドでのみ設定できます。このフィールドを更新するには、「**[!UICONTROL リセット]**」を選択して、新しいフロービジュアライゼーションを作成します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_pathingdimension"
>title="パスディメンション"
>abstract="選択したコンポーネントに続くパスや選択したコンポーネントから来るパスとして使用するディメンションを選択します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_container"
>title="フローコンテナ"
>abstract="パス（の数値）の表示に使用するコンテナを選択します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_disabled"
>title="繰り返しを含める（無効）"
>abstract="繰り返しは、複数値のディメンションを含むフロービジュアライゼーションから削除できません。"

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_default"
>title="繰り返しを含める"
>abstract="フロービジュアライゼーションは、ディメンションのインスタンスに基づいています。この設定により、ページのリロードなど、繰り返し発生するインスタンスを含めるか除外するかを選択できます。"

>[!CONTEXTUALHELP]
>id="workspace_flow_limit_occurrence"
>title="最初 / 最後の発生に制限"
>abstract="結果は、最初／最後のタッチポイントが入口か出口である場合のパスのみに制限されます。"

>[!CONTEXTUALHELP]
>id="workspace_flow_numberofcolumns"
>title="列の数"
>abstract="このフィールドは、最初のビルドでのみ設定できます。このフィールドを更新するには、「**[!UICONTROL リセット]**」を選択して、新しいフロービジュアライゼーションを作成します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_itemsexpandedpercolumn"
>title="列ごとに展開される項目数"
>abstract="このフィールドは、最初のビルドでのみ設定できます。このフィールドを更新するには、「**[!UICONTROL リセット]**」を選択して、新しいフロービジュアライゼーションを作成します。"

>[!CONTEXTUALHELP]
>id="workspace_flow_resettoupdate"
>title="リセットして更新"
>abstract="このフィールドは、最初のビルドでのみ設定できます。このフィールドを更新するには、「**[!UICONTROL リセット]**」を選択して、新しいフロービジュアライゼーションを作成します。"


フロービジュアライゼーションは、web サイトやアプリ上の特定のコンバージョンイベントに起因するジャーニーを理解するのに役立ちます。 または、特定のコンバージョンイベントに至る。 ビジュアライゼーションは、ディメンション（およびディメンション項目）または指標を通過するパスをトレースします。

目的のパスの開始または終了を設定できます。 または、ディメンションまたはディメンション項目を流れるすべてのパスを分析します。
![新しいフロー UI](assets/new-flow.png)

## 使用

1. ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL フロー]**&#x200B;ビジュアライゼーションを追加します。[パネルへのビジュアライゼーションの追加](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)を参照してください。

1. 次のオプションのいずれかを使用して、フロービジュアライゼーションを固定します。

   * [!UICONTROL **次で始まる**]（指標、ディメンション、または項目）、
   * [!UICONTROL **次を含む**]（ディメンション、または項目）、
   * [!UICONTROL **次で終わる**]（指標、ディメンションまたは項目）

   これらの各カテゴリは、画面上に&#x200B;*ドロップゾーン*&#x200B;として表示されます。ドロップゾーンは、次の 3 つの方法で設定できます。

   * ドロップダウンメニューを使用して、指標またはディメンションを選択する。
   * ディメンションまたは指標を左側のパネルからドラッグします。
   * ディメンションまたは指標の名前を入力し始め、ドロップダウンリストに表示されたら選択します。

   >[!IMPORTANT]
   >
   >計算指標を「**[!UICONTROL 次で始まる]**」または「**[!UICONTROL 次で終わる]**」フィールドで使用することはできません。

1. 指標を選択する場合は、次に示すように、使用する&#x200B;[!UICONTROL **パスディメンション**]&#x200B;を提供し、そのパスディメンションを、選択したコンポーネントへのパスまたは選択したコンポーネントからのパスとして使用する必要があります。デフォルトは「[!UICONTROL **ページ**]」です。

   ![フロー設定](assets/flow-configure.png)

1. （オプション）「**[!UICONTROL 詳細設定を表示]**」を選択して、次のいずれかのオプションを設定します。


   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL ラベルの折り返し]** | 通常、フロー要素のラベルは、画面の領域を節約するために切り捨てられます。しかし、このチェックボックスをオンにすることで完全なラベルを表示できます（デフォルト = オフ）。 |
   | **[!UICONTROL 繰り返しインスタンスを含める]** | フロービジュアライゼーションは、ディメンションのインスタンスに基づいています。この設定により、ページのリロードなど、繰り返し発生するインスタンスを含めるか除外するかを選択できます。ただし、listVar、listProp、s.product、マーチャンダイジング eVar など複数の値を持つディメンションを含むフロービジュアライゼーションから、繰り返しを削除することはできません。 <p>このオプションはデフォルトでは無効です。</p> |
   | **[!UICONTROL 最初／最後の発生件数に制限]** | パスを、ディメンション、項目、指標の、最初または最後の発生件数で始まるパスまたは終わるパスに制限します。詳しくは、[最初／最後の発生件数に制限](#example-scenario-for-limit-to-firstlast-occurrence)を参照してください。 |
   | **[!UICONTROL 列の数]** | フロー図で必要な列数最大 5 列まで指定できます。 |
   | **[!UICONTROL 列ごとに展開される項目数]** | 各列に必要な項目数1 列につき最大 10 個の展開項目を指定できます。 |
   | **[!UICONTROL フローコンテナ]** | **[!UICONTROL 訪問]** と **[!UICONTROL 訪問者]** を切り替えて、パスを分析できます。 これらの設定により、訪問者のエンゲージメントを（訪問全体にわたって）訪問者レベルで把握したり、分析を 1 回の訪問に制限したりできます。 |

   >[!IMPORTANT]
   >
   >**[!UICONTROL 列数]**&#x200B;と&#x200B;**[!UICONTROL 列ごとに展開される項目数]**&#x200B;の組み合わせにより、フロービジュアライゼーションの作成に必要な基になるリクエストの数を決定します。これらの数が多いほど、ビジュアライゼーションのレンダリングに時間がかかります。


1. 「**[!UICONTROL 作成]**」を選択します。


### 例

ユーザーがサイト上で最も人気のあるページに出入りする経路を辿るとします。

1. フロービジュアライゼーションを作成します。
1. [!UICONTROL **ページ**]&#x200B;ディメンションを「**[!UICONTROL 次を含む]**」フィールドにドラッグし、「[!UICONTROL **作成**]」を選択します。
1. フロービジュアライゼーションは、ビジュアライゼーションの中央にあるフォーカスノードに最も多く閲覧されたページで構築されます。また、そのページにつながるトップページ（フォーカスノードの左側）と、そのページからつながるトップページ（フォーカスノードの右側）も表示されます。
1. フロー内のデータを分析します。詳しくは、[設定](#configure)を参照してください。


## 設定

ビジュアライゼーションの上部に、フロー設定の概要が表示されます。図のパスは比例します。アクティビティの多いパスは太く表示されます。

![訪問回数、パスディメンション：ページ、フローコンテナ：訪問者数で終わるを示すフロー出力の例。](assets/flow-output.png)

データをさらに詳しく調べるには、次の複数のオプションがあります。

* フロー図はインタラクティブです。図にマウスポインターを置いて、表示する詳細情報を変更します。

* 図でノードを選択すると、そのノードの詳細が表示されます。 折りたたむには、もう一度ノードを選択します。

  フロービジュアライゼーションで複数のノードを展開したままにすると、レポート時間に影響を与える可能性があります。 一般的なガイドラインとして、一度に展開し続けるノードは 10 個以下にしてください。

  ![ノードの詳細を示すインタラクティブフロー図の例。](assets/node-details.png)

* 列にフィルターを適用して、特定の結果（包含や除外、除外する、条件を指定するなど）のみを表示できます。

* 左側または右側の ![AddCircle](/help/assets/icons/AddCircle.svg) を選択して、列を展開します。

* 出力をカスタマイズするには、「[コンテキストメニュー](#context-menu)」オプションを使用します。

* フローを編集するか、別のオプションで再作成するには、構成の概要の横にある ![編集](/help/assets/icons/Edit.svg) を選択します。

## フィルター

各列の上にポインタを合わせると、フィルター ![フィルター](/help/assets/icons/Filter.svg) が表示されます。このフィルターを選択すると、フリーフォームテーブルに存在するのと同じフィルターダイアログが表示されます。[フィルタリングと並べ替え](freeform-table/../../freeform-table/filter-and-sort.md)を参照してください。

* **[!UICONTROL 詳細を表示]**&#x200B;を使用し、詳細設定を設定して、演算子のリストに特定の条件を含めたり、除外したりすることができます。詳しくは、[フィルタリングと並べ替え](../freeform-table/filter-and-sort.md)を参照してください。
* 列をフィルタリングすると、その特定の列にフィルタリングが反映されます。青色の ![フィルター](/help/assets/icons/FilterColored.svg) は、列がフィルタリングされていることを示します。フィルターでは、列が縮小されてフィルターで許可された項目のみが表示されます。または、フィルターに必要な 1 つの項目を除くすべての項目が削除されます。
* 残りのノードへのデータフローがある限り、すべてのダウンストリームおよびアップストリームの列は、維持されます。
* フィルターを削除するには、![フィルター](/help/assets/icons/Filter.svg) を選択して、フィルターメニューを開きます。適用されたフィルターを削除してから、「**[!UICONTROL 保存]**」をクリックします。フローは、フィルタリングされていない、以前の状態に戻ります。

## コンテキストメニュー

次のオプションを使用して、フロービジュアライゼーション内の任意のノードでコンテキストメニューを使用します。

| オプション | 説明 |
|--- |--- |
| **[!UICONTROL このノードにフォーカス]** | 選択したノードにフォーカスを変更します。フロー図の中央にフォーカスノードが表示されます。 |
| **[!UICONTROL やり直し]** | 新しいフロー図を作成できる、フリーフォーム図ビルダーに戻ります。 |
| **[!UICONTROL このパスのフィルターを作成]** | フィルターを作成します。この選択では、新しいフィルターを設定できる、フィルタービルダーに移動します。 |
| **[!UICONTROL 分類]** | 利用可能なディメンション、指標、時間でノードを分類します。 |
| **[!UICONTROL フィルター列]** | フリーフォームテーブルで使用できるのと同じフィルターオプションが表示されます。使用可能なオプションについて詳しくは、[テーブルのフィルタリングと並べ替え](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)の「テーブルへのシンプルなフィルターまたは高度なフィルターの適用」の節を参照してください。 |
| **[!UICONTROL 項目を除外]**&#x200B;または&#x200B;**[!UICONTROL 除外した項目を復元]** | 列から特定のノードを削除して、列の上部にフィルターとして自動的に作成します。除外した項目を復元するには、コンテキストメニューから、「**[!UICONTROL 除外した項目を復元]**」を選択します。また、列の上部にあるフィルターを開いて、先ほど除外した項目を含むピルボックスを削除することもできます。 |
| **[!UICONTROL トレンド]** | ノードのトレンド図を作成します。 |
| **[!UICONTROL 次の列を表示]**／**[!UICONTROL 前の列を表示]** | ビジュアライゼーションの次の（右）列または前の（左）列を表示します。 |
| **[!UICONTROL 列を非表示]** | 選択されている列をビジュアライゼーションから非表示にします。 |
| **[!UICONTROL 列全体を展開]** | 列を展開して、すべてのノードを表示します。デフォルトでは、上位 5 つのノードのみ表示されます。 |
| **[!UICONTROL 選択内容からオーディエンスを作成]** | 選択した列に基づいてオーディエンスを作成します。 |
| **[!UICONTROL 列全体を折りたたむ]** | すべてのノードを列内に隠します。 |

## 最初 / 最後の発生に制限

このオプションを使用する場合、次の点に注意してください。

* **[!UICONTROL 最初 / 最後の発生に制限]**&#x200B;は、シリーズの最初または最後の発生のみをカウントします。**[!UICONTROL 次で始まる]**&#x200B;または&#x200B;**[!UICONTROL 次で終わる]**&#x200B;条件の他のすべての発生は、破棄されます。
* **[!UICONTROL 次で始まる]**フローで使用していた場合、開始条件に一致する最初の発生のみが含まれます。
次の例では、フロー内の各ステップにおける*買い物かごに追加*&#x200B;と&#x200B;*製品メインカテゴリ*&#x200B;の&#x200B;**すべて**の発生件数が含まれます。
  ![制限なし、最初](assets/limitofffirst.png)

  次の例では、フローの各ステップにおける&#x200B;*買い物かごに追加*&#x200B;と&#x200B;*製品メインカテゴリ*&#x200B;の&#x200B;**最初**の発生件数のみが含まれます。
  ![リント、開始](assets/limitonfirst.png)
* **[!UICONTROL 次で終わる]**フローで使用していた場合、終了条件に一致する最後の発生のみが含まれます。
次の例では、フロー内の各ステップにおける*製品メインカテゴリ*&#x200B;と&#x200B;*買い物かごに追加*&#x200B;の&#x200B;**すべて**の発生件数が含まれます。
  ![制限なし、最初](assets/limitofflast.png)

  次の例では、フローの各ステップにおける&#x200B;*製品メインカテゴリ*&#x200B;と&#x200B;*買い物かごに追加*&#x200B;の&#x200B;**最後**の発生のみが含まれます。
  ![リント、開始](assets/limitonlast.png)
* 使用される系列は、コンテナに基づいて異なります。**[!UICONTROL 訪問者]** コンテナを使用している場合、一連のイベントは訪問数です。 **[!UICONTROL 訪問者]** コンテナを使用している場合、一連のイベントは、指定された日付範囲での指定されたユーザーに対するすべてのヒットです。
* 「**[!UICONTROL 最初／最後の発生に制限]**」オプションは、「**[!UICONTROL 次で始まる]**」または「**[!UICONTROL 次で終わる]**」フィールドで指標またはディメンション項目を使用している場合に、詳細設定で設定できます。


>[!MORELIKETHIS]
>
>[パネルへのビジュアライゼーションの追加](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[ビジュアライゼーション設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[ビジュアライゼーションコンテキストメニュー](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


<!--
## Create a flow visualization {#configure}

1. Add a blank panel to your project and click the visualizations icon in the left rail. 

   Or
   
   Add a visualization in any of the ways described in the "Add visualizations to a panel" section in [Visualizations overview](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Anchor your Flow visualization using one of the following options:

   * [!UICONTROL **Starts with**] (metrics, dimensions, or items), or
   * [!UICONTROL **Contains**] (dimensions, or items), or
   * [!UICONTROL **Ends with**] (metrics, dimensions, or items)

   Each of these categories is shown onscreen as a "drop zone." You can populate the drop zone in 3 ways:

   * Use the drop-down menu to select metrics or dimensions.
   * Drag dimensions or metrics from the left rail.
   * Begin typing the name of a dimension or metric, then select it when it appears in the drop-down list.

   >[!IMPORTANT]
   >
   >Calculated metrics cannot be used in the  **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** fields.

1. If you choose a metric, you also need to provide a [!UICONTROL **Pathing Dimension**] to use as your path leading to or coming from your selected component, as shown here. The default is [!UICONTROL **Page**].

   ![pathing dimension](assets/pathing-dim.png)

1. (Optional) Select **[!UICONTROL Show advanced settings]** to configure any of the following options:

   ![advanced settings](assets/adv-settings.png)

   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Normally, the labels on the Flow elements are truncated to save screen real estate, but you can make the entire label visible by checking this box.  Default = unchecked. |
   | **[!UICONTROL Include repeat instances]** | Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, e.g. Page reloads. However, repeats cannot be removed from Flow visualizations that include multi-valued dimensions, such as listVars, listProps, s.product, merchandising eVars, etc. <p>This option is disabled by default.</p> |
   | **[!UICONTROL Limit to first/last occurrence]** | Limit paths to those that start/end with the first/last occurrence of a dimension/item/metric. See the section below, [Example scenario for 'limit to first/last occurrence'](#example-scenario-for-limit-to-firstlast-occurrence), for a more detailed explanation. |
   | **[!UICONTROL Number of columns]** | The number of columns you want in your Flow diagram. You can specify a maximum of 5 columns. |
   | **[!UICONTROL Items expanded per column]** | The number of items you want in each column. You can specify a maximum of 10 items expanded per column.  |
   | **[!UICONTROL Flow container]** | <ul><li>Visit</li><li>Visitor</li></ul> Lets you switch between Visit and Visitor to analyze visitor pathing. These settings help you understand visitor engagement at the visitor level (across visits), or constrain the analysis to a single visit.|

   >[!IMPORTANT]
   >
   >The combination of **[!UICONTROL Number of columns]** and **[!UICONTROL Items expanded per column]** determine the number of underlying requests required to create the flow visualization. The higher those numbers, the longer it takes to render a visualization.

1. Select **[!UICONTROL Build]**.

>[!INFO]
>
>**Example:** Suppose that you want to trace the path that users took both to and from the most popular pages on your site.
>
>To do this, you would
> 
>1. Begin creating a flow visualization as described above.
>1. Drag the [!UICONTROL **Page**] dimension into the **[!UICONTROL Contains]** field, then select [!UICONTROL **Build**].
>1. The Flow visualization builds with the most-viewed page visible in the focus node in the center of the visualization. You also see the top pages leading into that page (to the left of the focus node) as well as the top pages leading out of that page (to the right of the focus node).
>1. Analyze data in the flow, as described in [View and change the Flow output](#view-and-change-the-flow-output).


## View and change the Flow output {#output}

![flow output](assets/flow-output.png)

A summary of the Flow configuration appears at the top of the diagram. The thickness of a path in the diagram is proportional to its activity, with paths with more activity appearing thicker than those with less activity.

To drill down further into the data, you have several options:

* The flow diagram is interactive. Mouse over the diagram to change the details that are shown.

* When you select on a node in the diagram, the details for that node appear. Select on the node again to collapse it.

   ![node-details](assets/node-details.png)

* You can filter a column to display only certain results, such as including and excluding, specifying criteria, and so forth.

* Select the plus sign (+) on the left to expand a column.

* Use the right-click options explained below to further customize the output.

* Select the pencil icon next to the configuration summary to further edit the flow or rebuild it with different options.

* You can also export and further analyze your Flow diagram as part of a project's .CSV file by going to **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

## Filtering

Above each column, a filter appears when you hover over it. By selecting the filter, you get the same filter dialog that exists in the Freeform table today. This filter works the same as it does in the Freeform table.

* Use advanced settings to include or exclude certain criteria with our list of operators.
* Once you have filtered an item from the list, that specific column will reflect the filtering. (The filter either reduces it to only show the item allowed in the filter, or it removes all items except for the one item you want in the filter.
* All downstream and upstream columns should persist, as long as there is data flowing into the remaining nodes.
* Once applied, the filter icon appears in blue above the column it is filtering.
* To remove a filter, select the filter icon to open the filter menu. Remove any filters applied and then select **[!UICONTROL Save]**. The flow should return to its previous, unfiltered state.

## Right-click options {#right-click}

| Option | Description |
|--- |--- |
| [!UICONTROL Start over] | Returns you to the Freeform diagram builder, where you can build a new Flow diagram. |
| [!UICONTROL Create segment for this path] | Create a segment. This takes you into the Segment Builder, where you can configure the new segment. |
| [!UICONTROL Breakdown] | Break the node down by available Dimensions, Metrics, or Time. |
| [!UICONTROL Trend] | Create a trended diagram for the node. |
| Show next column / Show previous column | Reveals the next (right) or previous (left) column of the visualization. |
| Hide column | Hides the selected column from the visualization. | 
| [!UICONTROL Expand entire column] | Expand a column to show all nodes. By default, only the top five nodes display. |

## Example scenario for 'limit to first/last occurrence'

When using this option, keep in mind that:

* **[!UICONTROL Limit to first/last occurrence]** counts only the first/last occurrence in the series. All other occurrences of the **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** criteria are discarded.
* If used with a **[!UICONTROL Starts with]** flow, only the first occurrence that matches the start criteria is included.
* If used with an **[!UICONTROL Ends with]** flow, only the last occurrence that matches the end criteria will be included.
* The series used differs based on the container. If using the **[!UICONTROL Visit]** container, the series of hits will be the session. If using the **[!UICONTROL Visitor]** container, the series of hits will be all the hits for a given user in the provided date range.
* The **[!UICONTROL Limit to first/last occurrence]** option can be configured in the advanced settings when using a Metric or Dimension Item in the "Starts with" or "Ends with" fields.

Example series of hits:

Home > Products > Add to cart > Products > Add to Cart > Billing > Order Confirmation

### Consider a flow analysis using the following settings:

* Start with[!UICONTROL  Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container

If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of hits counts 2 occurrences of "Add to Cart".
Expected Flow Output:
"Add to Cart" (2) —> "Products" (1)
                  -> "Billing" (1)

However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the first occurrence of "Add to cart" is included in the analysis.
Expected Flow Output:
"Add to Cart" (1) —> "Products" (1)

### Consider the same series of hits but using the following settings:

* Ends with [!UICONTROL Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container

If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of hits would count 2 occurrences of "Add to Cart".
Expected Flow Output:
"Products" (2) <— "Add to cart" (2)

However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the last occurrence of [!UICONTROL Add to cart] would be included in the analysis.
Expected Flow Output:
"Products" (1) <— "Add to cart" (1)

-->