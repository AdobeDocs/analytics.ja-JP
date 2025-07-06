---
description: ディメンション、指標、セグメントおよび関数をドラッグ&ドロップするためのキャンバスを提供し、コンテナ階層ロジック、ルールおよび演算子に基づいてカスタム指標を作成するための計算指標ビルダーについて説明します。
title: 指標の作成
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 97%

---

# 計算指標の作成 {#build-metrics}

Adobe Analytics には、ディメンション、指標、セグメントおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルール、演算子に基づいてカスタム指標を作成できる、キャンバスが用意されています。この統合開発ツールでは、シンプルまたは複雑な計算指標を作成および保存できます。

計算指標ビルダーを使用して、計算指標を作成または編集できます。この方法で作成すると、コンポーネントリストで計算指標を使用できるようになります。このリストは、組織全体のプロジェクトで使用できます。または、[指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md)の[単一プロジェクトの計算指標の作成](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)の説明に従って、作成されたプロジェクトでのみ使用可能な計算指標をすばやく作成することもできます。

[計算指標の作成](../cm-workflow.md)では、新しい計算指標の作成に使用できる様々なオプションについて説明します。

## 計算指標ビルダーのエリア

**[!UICONTROL 計算指標ビルダー]**&#x200B;ダイアログは、新しい計算指標の作成または既存の計算指標の編集に使用します。ダイアログのタイトルは、[[!UICONTROL 計算指標]マネージャー](../cm-manager.md)から作成または管理する指標の場合、**[!UICONTROL 新しい計算指標]**&#x200B;または&#x200B;**[!UICONTROL 計算指標を編集]**&#x200B;になります。

>[!BEGINTABS]

>[!TAB 計算指標ビルダー]

![次の節で説明するフィールドとオプションを表示する計算指標の詳細ウィンドウ。](assets/calculated-metric-builder.png)

>[!TAB 計算指標の作成または編集]

![次の節で説明するフィールドとオプションを表示する計算指標の詳細ウィンドウ。](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 次の詳細を指定します（![必須](/help/assets/icons/Required.svg)は必須です）。

   | 要素 | 説明 |
   | --- | --- |
   | **[!UICONTROL レポートスイート]** | 計算指標のレポートスイートを選択できます。定義した計算指標は、選択したレポートスイートに基づいて、Workspace プロジェクトで使用できます。 |
   | **[!UICONTROL プロジェクトのみの指標]** | [単一プロジェクトの計算指標の作成](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)の説明に従って、単一プロジェクト用に作成された計算指標を編集すると、このダイアログの上部に情報ボックスが表示されます。 <p>この計算指標をすべてのプロジェクトで使用できるようにする場合は、「**[!UICONTROL この指標をすべてのプロジェクトで使用できるようにし、コンポーネントリストに追加]**」オプションを選択します。</p> |
   | **[!UICONTROL タイトル]** ![必須](/help/assets/icons/Required.svg) | 計算指標に名前を付けます（例：`Conversion Rate`）。 |
   | **[!UICONTROL 説明]** | セグメントの説明を入力します（例：`Calculated metric to define the conversion rate.`）。計算指標の数式は既に[!UICONTROL 概要]で自動的に使用できるので、数式を説明する必要はありません。 |
   | **[!UICONTROL 形式]** | 計算指標の形式を選択します。**[!UICONTROL 小数]**、**[!UICONTROL 時間]**、**[!UICONTROL 割合]**、**[!UICONTROL 通貨]**&#x200B;から選択できます。 |
   | **[!UICONTROL 小数点以下の桁数]** | 選択した形式の小数点以下の桁数を指定します。選択した形式が小数、通貨、割合である場合にのみ有効になります。 |
   | **[!UICONTROL 上昇傾向を次の形式で表示]** | 計算指標の上昇傾向を▲ **[!UICONTROL 良好（緑色）]**&#x200B;として表示するか、▼ **[!UICONTROL 不良（赤色）]**&#x200B;として表示するかを指定します。 |
   | **[!UICONTROL 通貨]** | 計算指標の通貨を指定します。選択した形式が通貨である場合にのみ有効になります。 |
   | **[!UICONTROL タグ]** | 1 つ以上のタグを作成または適用して、計算指標を整理します。入力を開始すると、選択できる既存のタグが見つかります。または、**[!UICONTROL Enter]** キーを押して新しいタグを追加します。「![CrossSize75](/help/assets/icons/CrossSize75.svg)」を選択して、タグを削除します。 |
   | **[!UICONTROL プレビュー]** | プレビューは過去 90 日間をカバーしており、指標が正しく定義されているかどうかを判断するための手段となります。 |
   | **[!UICONTROL 概要]** | 計算指標の定義の概要を表示します。<br/>例：![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 合計注文数]** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL セッション]**。 |
   | **[!UICONTROL 定義]** ![必須](/help/assets/icons/Required.svg) | [定義ビルダー](#definition-builder)を使用して、セグメントを定義します。 |

1. 計算指標の定義が正しいかどうかを確認するには、計算指標の結果の絶えず更新される&#x200B;**[!UICONTROL プレビュー]**&#x200B;を使用します。**[!UICONTROL プレビュー]**&#x200B;は過去 90 日間をカバーしており、計算指標の定義を継続的に評価します。

   **[!UICONTROL 製品の互換性]**&#x200B;は、計算指標と Adobe Analytics 機能の互換性を示します。詳しくは、[指標の互換性](/help/components/c-calcmetrics/cm-compatibility.md)を参照してください。

1. 次のいずれかを選択します。
   * 計算指標を保存する場合は、「**[!UICONTROL 保存]**」。
   * 計算指標のコピーを保存する場合は、「**[!UICONTROL 名前を付けて保存]**」。
   * 計算指標に対して行った変更をキャンセルするか、新しい計算指標の作成をキャンセルする場合は、「**[!UICONTROL キャンセル]**」。


## 定義ビルダー

定義ビルダーを使用すると、ディメンション、指標、セグメントおよび関数をドラッグ＆ドロップして、コンテナ階層ロジック、ルールおよび演算子に基づいてカスタム指標を作成できます。この作成では、標準指標、アドビ定義の指標、計算指標、セグメント、ディメンションおよび関数を使用できます。これらのコンポーネントはすべて、計算指標ビルダーのコンポーネントパネルから使用できます。さらに、演算子やコンテナも定義で使用できます。

![計算指標を作成](assets/create-calculated-metric.gif)

**[!UICONTROL 定義]**&#x200B;エリアでは、指標のみが単一のコンポーネントとして定義されます。その他のコンポーネントはすべて、コンテナ、ラッピング指標またはその他のコンテナとして定義されます。詳しくは、[コンテナ](#containers)を参照してください。

### 指標

指標を追加するには：

* コンポーネントパネルから ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 指標]**&#x200B;コンポーネントを&#x200B;**[!UICONTROL ここに指標、ディメンション、ディメンション項目、セグメント、関数をドラッグ＆ドロップ]**&#x200B;にドラッグ＆ドロップします。コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定のコンポーネントを検索できます。

定義の一部として計算指標を使用すると、その計算指標が展開されます。

指標を変更するには：

1. **[!UICONTROL 定義]**&#x200B;エリアの指標コンポーネントで「![設定](/help/assets/icons/Setting.svg)」を選択します。
1. ポップアップダイアログで、指標のタイプとアトリビューションモデルを定義できます。[指標タイプとアトリビューション](m-metric-type-alloc.md)を参照してください。

指標を削除するには：

* 指標の「![閉じる](/help/assets/icons/Close.svg)」を選択します。

### 演算子

演算子を使用すると、コンポーネント間またはコンテナ間の演算子を指定できます。以下の項目の間には演算子が自動的に表示されます。

* コンテナ内の 2 つ以上の指標
* コンテナ内の 2 つ以上のコンテナ
* コンテナ内の 1 つ以上の指標と 1 つ以上のコンテナ

以下を選択できます。

| 記号 | 演算子 |
|:---:|---|
| ![除算](/help/assets/icons/Divide.svg) | 除算（デフォルト） |
| ![閉じる](/help/assets/icons/Close.svg) | 乗算 |
| ![削除](/help/assets/icons/Remove.svg) | 減算 |
| ![追加](/help/assets/icons/Add.svg) | 追加 |

### 静的な数値

計算指標の定義に静的な数値を追加できます。静的な数値を追加するには：

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]**&#x200B;を選択します。
* 「**[!UICONTROL 静的な数値]**」を選択します。静的な数値コンテナが表示されます。
* 「[!UICONTROL *クリックして値を追加*]」を選択し、値を入力します。


### コンテナ

ディメンション、セグメントおよび関数をコンテナとして計算指標の定義に追加します。また、汎用コンテナを追加することもできます。コンテナは数式のように機能し、演算の順序を指定します。コンテナ内のものはすべて、次のコンポーネントまたはコンテナの前に処理されます。


#### セグメントコンテナ

セグメントコンテナの概念を使用すると、[セグメント適用済み指標](metrics-with-segments.md)を作成できます。セグメントコンテナを作成するには、セグメントを使用するか、ディメンションから作成したセグメントを使用します。

* ディメンションからセグメントコンテナを追加するには：

   1. コンポーネントパネルから ![ディメンション](/help/assets/icons/Dimensions.svg) **[!UICONTROL ディメンション]**&#x200B;コンポーネントを&#x200B;**[!UICONTROL ここに指標、ディメンション、ディメンション項目、セグメント、関数をドラッグ＆ドロップ]**&#x200B;にドラッグ＆ドロップします。コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定のコンポーネントを検索できます。
   1. **[!UICONTROL ディメンションからセグメントを作成]**&#x200B;ポップアップで、セグメントの条件を定義します。演算子のリストから選択し、値を選択するか入力します。例えば、**[!UICONTROL 月]** **[!UICONTROL 次に等しい]** ![ChevronDown](/help/assets/icons/ChevronDown.svg)`Sep 2024` などとなります。
   1. 「**[!UICONTROL 完了]**」を選択します。セグメントコンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に追加されます。


* セグメントからセグメントコンテナを追加するには、以下を使用します。

   * コンポーネントパネルから ![セグメント化](/help/assets/icons/Segmentation.svg) **[!UICONTROL セグメント]**&#x200B;コンポーネントを&#x200B;**[!UICONTROL ここに指標、ディメンション、ディメンション項目、フィルター、関数をドラッグ＆ドロップ]**&#x200B;にドラッグ＆ドロップします。コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定のセグメントを検索できます。
セグメントの名前を使用すると、セグメントコンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に自動的に追加されます。

   * コンポーネントパネルから![セグメント化](/help/assets/icons/Segmentation.svg) **[!UICONTROL セグメント]**&#x200B;コンポーネントを汎用コンテナにドラッグ＆ドロップします。コンテナがセグメントコンテナに変更されます。

   * コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]**&#x200B;を選択します。

      1. 「**[!UICONTROL セグメント]**」を選択します。セグメントコンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に追加されます。
      1. 新しいセグメントコンテナで、[!UICONTROL *選択…*]&#x200B;ドロップダウンメニューからセグメントを選択します。

  >[!TIP]
  >
  >複数のセグメントをコンテナに追加できます。

  コンテナ内のセグメントは、セグメントコンポーネントにちなんで名前が付けられます。例えば、![セグメント化](/help/assets/icons/Segmentation.svg) **[!UICONTROL web セッション]**&#x200B;などです。![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、セグメントの詳細を含んだポップアップが表示されます。このポップアップで、![編集](/help/assets/icons/Edit.svg) を選択して、セグメント定義を編集します。

コンテナからセグメントを削除するには：

* セグメント名の横にある ![閉じる](/help/assets/icons/Close.svg) を選択します。

詳細と例については、[セグメント化済み指標](metrics-with-segments.md)を参照してください。

#### 関数コンテナ

関数コンテナを追加するには、次の手順を使用します。

* ドラッグ＆ドロップ：

   1. コンポーネントパネルから ![関数](/help/assets/icons/Effect.svg) **[!UICONTROL 関数]**&#x200B;コンポーネントを「**[!UICONTROL ここに指標、ディメンション、ディメンション項目、セグメント、関数をドラッグ＆ドロップ]**」にドラッグ＆ドロップします。コンポーネントバーの ![検索](/help/assets/icons/Search.svg) を使用して、特定の関数を検索できます。
   1. 関数の名前を使用すると、関数コンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に自動的に追加されます。

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]**&#x200B;を選択します。

   1. 「**[!UICONTROL 関数]**」を選択します。
   1. コンテナで、[!UICONTROL *選択…*]&#x200B;ドロップダウンメニューから関数を選択します。

関数コンテナの名前は、関数コンポーネントの名前を取って付けられます。例：![関数](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT (metric)]**。![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、機能の詳細を含むポップアップが表示されます。関数について詳しくは、「**[!UICONTROL 詳細情報]**」を選択してください。

関数の使用方法と計算指標の作成に使用できる関数について詳しくは、[関数の使用](cm-using-functions.md)を参照してください。


#### 汎用コンテナ

汎用コンテナを追加するには：

* コンテナ内から ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 追加]**&#x200B;を選択します。
* 「**[!UICONTROL コンテナ]**」を選択します。 新しい空の汎用コンテナが&#x200B;**[!UICONTROL 定義]**&#x200B;に追加されます。汎用コンテナを使用して、計算指標の定義で階層をネストまたは作成できます。


#### 接続の削除

コンテナを削除するには、コンテナレベルで ![閉じる](/help/assets/icons/Close.svg) を選択します。

>[!MORELIKETHIS]
>
>[関数の使用](cm-using-functions.md)
>&#x200B;>[セグメント](/help/components/segmentation/seg-overview.md)
>


<!--

Adobe Analytics provides a canvas to drag and drop dimensions, metrics, segments, and functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex calculated metrics.

## Begin building a calculated metric

You can use the calculated metric builder to create or edit calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. Alternatively, you can quickly create a calculated metric that is available only for the project where it was created, as described in [Create calculated metrics for a single project](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

Access the calculated metric builder to begin creating a calculated metric that is available in the component list. 

1. Access the calculated metric builder in any of the follows ways:

   * In Analysis Workspace, open a project, then select **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
   * In Analysis Workspace, open a project, then select the **Plus** icon next to the [!UICONTROL **Metrics**] section in the left rail.
   * In [!DNL Adobe Analytics], go to **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, then select **[!UICONTROL + Add]** at the top of the Calculated metrics page.

1. Continue with [Areas of the calculated metric builder](#areas-of-the-calculated-metrics-builder).

## Areas of the Calculated metrics builder

The following image and accompanying table explain some of the main areas and features of the Calculated metrics builder.

![](assets/cm_builder_ui.png)

| Location in image  | Name and function  |
|---|---|
| 1 | **Title:** Naming the metric is mandatory. You cannot save the metric unless it is named.  |
| 2 | **Description:** Give it a user-friendly description to show what it's used for and to distinguish it from similar ones. <p>The description also appears within a report. It's best NOT to put the formula into the description - instead, describe what this metric should and should not be used for. (The formula is generated as you build the metric, underneath the Summary heading. As a result, there is no need to add the formula to the description.) </p>  |
| 3 | **Format:** Choices include Decimal, Time, Percent, and Currency.  |
| 4 | **Decimal Places:** Shows how many decimal places will be shown in the report. The maximum number of decimal places you can specify is 10.  |
| 5| **Show Upward Trend As:** This metric polarity setting shows whether Analytics should consider an upward trend in the metric as good (green) or bad (red). As a result, the report's graph will show as green or red when it's going up.  |
| 6 | **Tags:** Tagging is a good way to organize metrics. All users can create tags and apply one or more tags to a metric. However, you can see tags only for those segments that you own or that have been shared with you. What kinds of tags should you create? Here are some suggestions for useful tags:<ul><li>**Team names**, such as Social Marketing, Mobile Marketing.</li><li>**Projects** (analysis tags), such as Entry-page analysis.</li><li>**Categories**, such as Women's; Geography.</li><li>**Workflows**, such as To be approved; Curated for (a specific business unit)</li></ul> |
| 7 | **Summary:** <p>The Summary formula updates anytime you make a change to the metric definition. This formula also shows up in the metrics rail on the left when you hover over a metric and click the <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icon. </p>  |
| 8 | **Definition:** This is where you drag in metrics/calculated metrics, segments, and/or functions to build the calculated metric. <ul><li>If you drag in a calculated metric, it will expand its metric definition automatically. </li> <li>You can nest definitions with containers. However, unlike segment containers, these containers function like a math expression and determine the order of operations. </li> </ul>  |
| 9 | **Operator:** Divided by ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) is the default operator, plus there are the +, -, and x operators. |
| 10 | **Preview:** Provides a quick read on any possible errors. The preview covers the last 90 days. This is a way of initially gauging whether you have selected the right components for your metric. An unexpected result would mean you need to take a second look at the metric definition.  |
| 11 | **Product compatibility:** Product compatibility shows you whether the metric is compatible with <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html"  > Current Data </a>, with Fully Processed Data, or only with Marketing Channel reports (first-touch allocation). <p>Note:  Current Data does not support all metrics. Metrics that contain segments or functions are not compatible with current data. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > More... </a> </p> </p>  |
| 12 | **Add:** For all types of calculated metrics, you can add containers and static numbers to the definition. For advanced calculated metrics, you can also add segments and functions. <ul><li>Containers function like a math expression and determine the order of operations. So anything in a container will get processed before the next operation.</li><li>Dragging a segment onto a container segments everything in that container. (Advanced calculated metrics only)</li><li>You can stack multiple segments in a container.</li></ul> |
| 13 | **Gear icon (Metric Type, Attribution):** Selecting the gear icon next to a metric lets you specify the <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > metric type and attribution models </a>. |
| 14 | **New:** Lets you create a new component, such as a new segment (which takes you to the <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > Segment Builder </a>.) |
| 15 | **Search Components:** This search bar lets you search for dimensions, metrics, segments (advanced calculated metrics only), and functions (advanced calculated metrics only). |
| 16 | **List of Dimensions:** Rather than leaving the Calculated Metric Builder in order to build a simple segment (in the Segment Builder), e.g. "Page = Homepage", you can drag in Page and select Homepage directly from the Calculated Metric Builder.<p>This results in a much more streamlined workflow for creating segmented calculated metrics.</p> |
| 17 | **List of Metrics:** Metrics come in 3 categories: <ul> <li>Standard metrics (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Calculated metrics ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Metrics templates ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - at the bottom of the list. </li> </ul> <p>When you hover over a metric, you can see the Info icon to the right of it: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Clicking this icon gives you the following information: </p><ul> <li>The formula of how it is calculated. </li><li>A preview trend of the metric. </li><li>An edit (pencil) icon <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> at the top right that will take you to the Calculated Metrics Builder where you can edit this calculated metric. </li></ul> |
| 18 | **List of Segments:** (Advanced calculated metrics only) As an Admin, this list shows all segments created in your login company. If you are a non-Admin user, this list shows segments you own and those shared with you. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html"  > More... </a> |
| 19 | **List of Functions:** (Advanced calculated metrics only) Functions are divided into two lists: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Basic </a> (used most often) and <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Advanced </a>. |
| 20 | **Report Suite selector:** Lets you switch to a different report suite. |

{style="table-layout:auto"}

-->
