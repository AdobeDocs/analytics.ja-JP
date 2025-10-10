---
description: Analysis Workspace のプロジェクトでのコンポーネントの使用方法について説明します。
title: プロジェクトでのコンポーネントの使用
feature: Workspace Basics
role: User, Admin
exl-id: fb56e794-67e3-4f85-960e-b90684300fa0
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 82%

---

# プロジェクトでのコンポーネントの使用

コンポーネントは、Analysis Workspace において、あらゆるプロジェクトの実際のデータを作成します。コンポーネントは、ディメンション、指標、セグメントおよび日付範囲で構成されています。コンポーネントをビジュアライゼーションまたはパネルにドラッグすることで、プロジェクトに追加できます。

追加できるコンポーネントのタイプについて詳しくは、[コンポーネントの概要](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)を参照してください。

>[!TIP]
>
>各コンポーネントの詳細については、![InfoOutline](/help/assets/icons/InfoOutline.svg) を使用してください。詳しくは、[コンポーネント情報](#component-info)を参照してください。

## プロジェクトへのコンポーネントの追加

1. [Analysis Workspace で新しいプロジェクトを作成します](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)。

1. Analysis Workspace のプロジェクトに[パネルを追加](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)するか、[ビジュアライゼーションを追加](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)します。空のプロジェクトにコンポーネントを追加すると、フリーフォームテーブルビジュアライゼーションが作成されます。

1. ボタンパネルから「![キュレート](/help/assets/icons/Curate.svg) **[!UICONTROL コンポーネント]**」を選択します。左側のパネルに、使用可能なすべてのコンポーネントが表示されます。詳しくは、[インターフェイス](/help/analyze/analysis-workspace/home.md#interface)を参照してください。

1. 追加するコンポーネントまでスクロールするか、それを検索し、プロジェクト内のパネルまたはビジュアライゼーションにドラッグします。

1. オプションで、コンポーネントをパネルヘッダーのセグメントドロップゾーンにドラッグできます。このドラッグ＆ドロップは、コンポーネントをセグメントとして定義し、そのセグメントをパネル内のすべてのコンテンツ適用します。パネル上のセグメントドロップゾーンを使用してパネルをセグメント化する方法について詳しくは、[&#x200B; パネルの概要 &#x200B;](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) の [&#x200B; ドロップゾーン &#x200B;](/help/analyze/analysis-workspace/c-panels/panels.md) を参照してください。

1. 詳しくは、次の節を参照してください。

   * [プロジェクトへのディメンションの追加](#add-dimensions-to-a-project)

   * [プロジェクトへの指標の追加](#add-metrics-to-a-project)

   * [プロジェクトへのセグメントの追加](#add-segments-to-a-project)

   * [プロジェクトへの日付範囲の追加](#add-date-ranges-to-a-project)

### プロジェクトへのディメンションの追加

[&#x200B; ディメンション &#x200B;](/help/components/dimensions/overview.md) は、通常、文字列値を含むAdobe Analyticsの変数です。 一方、[指標](/help/components/calculated-metrics/cm-overview.md)には、ディメンションに結び付く数値が含まれます。基本レポートは、文字列値（ディメンション）の行と数値（指標）の列を示します。

1. [プロジェクトへのコンポーネントの追加](#add-components-to-a-project)の説明に従って、まず、Analysis Workspace のプロジェクトにディメンションを追加します。

1. 次のいずれかの方法を選択して、ディメンションを追加し、分析するデータのタイプを決定します。

   ![ディメンションの追加](assets/add-dimension.gif)

   * ディメンションを Analysis Workspace のビジュアライゼーション（フリーフォームテーブルなど）にドラッグします。

   * [プロジェクトへのセグメントの追加](#add-filters-to-a-project)の説明に従って、左側のパネルから 1 つ以上のディメンションをセグメントドロップゾーンにドラッグして、クイックセグメントを作成します。

1. オプションで、Analysis Workspace 内のディメンションおよびディメンション項目を他のコンポーネントを使って分類できます。詳しくは、[Workspace でのディメンションの分類](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)を参照してください。

Analysis Workspace でのディメンションの使用方法について詳しくは、[ディメンションのプレビュー](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md)、[ディメンションの分類](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)および[時間分割ディメンション](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md)を参照してください。

### プロジェクトへの指標の追加

指標を使用すると、Analysis Workspace でデータポイントを数量化できます。これらは、ビジュアライゼーション内の列として最も一般的に使用され、ディメンションに関連付けられます。

Analysis Workspace のプロジェクトに指標を追加するには

1. [&#x200B; プロジェクトへのコンポーネントの追加 &#x200B;](#add-components-to-a-project) の説明に従って、Analysis Workspaceでプロジェクトに指標を追加し始めます。



1. Analysis Workspace に指標を追加するには、次のいずれかの方法を選択します。

   ![指標の追加](assets/add-metric.gif)

   * 指標を空のフリーフォームテーブルにドラッグすると、プロジェクトの日付期間にわたる指標のトレンドを確認できます。

   * ディメンションが存在する場合に指標をドラッグすると、各ディメンジョン項目にその指標が表示されます。

   * 既存の指標ヘッダーの上に指標をドラッグすると、置き換えることができます。

   * 右側にある既存の指標ヘッダーの左端に指標をドラッグして、新しい指標を追加します。

   * 既存の指標ヘッダーの上または下に指標をドラッグして、指標の重複を作成します。


詳しくは、[指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md)を参照してください。

### プロジェクトへのセグメントの追加

[セグメント](/help/components/segmentation/seg-overview.md)を使用すると、特性や特定のインタラクションに基づいて、ユーザー、セッションまたはイベントのサブセットを識別できます。

Analysis Workspace では、次のいずれかの方法でセグメントを使用できます。

* パネルへのセグメントの追加
パネルにセグメントを追加すると、そのセグメントはパネル内のすべてのコンテンツに適用されます。
パネル上のセグメントドロップゾーンを使用してパネルをセグメント化する方法について詳しくは、[&#x200B; パネルの概要 &#x200B;](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) の [&#x200B; ドロップゾーン &#x200B;](/help/analyze/analysis-workspace/c-panels/panels.md) を参照してください。

* ビジュアライゼーションへのセグメントの追加
フリーフォームテーブルの列にセグメントを追加すると、そのセグメントはテーブルの列内のすべてのコンテンツに適用されます。また、セグメントをフォールアウトビジュアライゼーションの一部として追加することもできます。

* コンポーネントでのセグメントの使用
[&#x200B; 計算指標 &#x200B;](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)、[&#x200B; 注釈 &#x200B;](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder) または [&#x200B; セグメント &#x200B;](/help/components/segmentation/segmentation-workflow/seg-build.md) などのコンポーネントを定義する場合、セグメントを定義の一部として使用できます。


### プロジェクトへの日付範囲の追加

[&#x200B; 日付範囲 &#x200B;](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) は、Analysis Workspaceでのレポート時間枠を決定します。 また、データ範囲は、プロジェクト内のパネルや、一部のビジュアライゼーション（フリーフォームテーブルなど）にも適用できます。

各パネルには、デフォルトで日付範囲が含まれています。パネルの日付範囲を更新するには、いくつかの方法があります。その方法の 1 つとして、左側のパネルから日付範囲コンポーネントをドラッグして、Analysis Workspace のパネルの日付範囲を更新します。

1. 必要に応じて、[プロジェクトへのパネルの追加](#add-components-to-a-project)の説明に従って、Analysis Workspace のプロジェクトに日付範囲を追加します。

1. 左側のパネルから日付範囲を次の場所にドラッグ&amp;ドロップします。

   * パネルの日付範囲を変更するための現在の日付範囲。

     ![日付範囲をドロップ](assets/add-date-range.gif)

   * フリーフォームテーブルビジュアライゼーションの指標またはディメンション。詳しくは、[日付範囲の使用](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#use-date-ranges)を参照してください。

Analysis Workspace での日付範囲の使用方法と管理方法について詳しくは、[日付範囲の概要](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)を参照してください。

## コンポーネント情報

任意のコンポーネントにポインターを合わせると、![詳細情報](/help/assets/icons/InfoOutline.svg)が表示されます。![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、コンポーネントに関する追加情報を含むポップアップが表示されます。

![コンポーネント情報](assets/component-info.png)

アクセス制御に基づいて、次の操作を実行できます。

* コンポーネントの ![ブックマーク](/help/assets/icons/Bookmark.svg) [!UICONTROL データディクショナリ]定義にアクセスします。
* コンポーネントが定義されている ![&#x200B; 編集 &#x200B;](/help/assets/icons/Edit.svg) コンポーネントビルダーにアクセスします。




<!--
# Use components in Analysis Workspace

Components make up the actual data of any project in Analysis Workspace. Components consist of dimensions, metrics, segments, and date ranges. You can add components to a project by dragging them into visualizations or panels.

For overview information about the types of components you can add, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

>[!TIP]
>
>For information about each component, select the Info icon next to a component's name in the left rail of Analysis Workspace, or see the [Analytics Components Guide](/help/components/home.md).

## Begin adding components to a project

1. [Create a project in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) if you haven't already.

1. [Add a panel](/help/analyze/analysis-workspace/c-panels/panels.md) or [add a visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) to the project in Analysis Workspace. 

   If you add a component to a blank project, a freeform table visualization is automatically created.

1. Select the **[!UICONTROL Components]** icon in the left rail.

   ![](assets/build-components.png)

1. Scroll to or search for the component you want to add, then drag it to a panel or visualization within your project. 

1. (Optional) Drag a component to the segment drop zone in a panel header. 

   Segments apply to all content within the panel.

   For information about how you can use the segment drop zone on a panel to filter your panel, see [Drop zone](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Panels overview](/help/analyze/analysis-workspace/c-panels/panels.md).

   ![drop a segment in the drop zone](assets/segment-dropzone.png)

1. For more detailed information, continue with one of the following sections, depending on the component type you are adding:

   * [Add dimensions to a project](#add-dimensions-to-a-project)

   * [Add metrics to a project](#add-metrics-to-a-project)

   * [Add segments to a project](#add-segments-to-a-project)

   * [Add date ranges to a project](#add-date-ranges-to-a-project)

## Add dimensions to a project

[Dimensions](/help/components/dimensions/overview.md) are variables in Adobe Analytics that typically contain string values. Common dimensions include [Page](/help/components/dimensions/page.md), [Referring domain](/help/components/dimensions/referring-domain.md), or an [eVar](/help/components/dimensions/evar.md). In contrast, [metrics](/help/components/metrics/overview.md) contain numeric values that tie to a dimension. A basic report shows rows of string values (dimension), against a column of numeric values (metric).

1. Start adding a dimension to your project in Analysis Workspace, as described in [Begin adding components to a project](#begin-adding-components-to-a-project).

1. Choose one of the following methods to add dimensions and determine the type of data you want to analyze:

   * Drag a dimension to a visualization (such as a freeform table) in Analysis Workspace.

     ![Add dimensions to a project](assets/add-dimensions.png)
   
   * Drag one or more dimensions from the left rail onto the segment drop zone to create an ad hoc segment, as described in [Add segments to a project](#add-segments-to-a-project).

     ![drop a segment in the drop zone](assets/segment-dropzone.png)

1. (Optional) You can break down dimensions and dimension items in Analysis Workspace with other components. 

   For more information, see [Break down dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).

For more information about how to use dimensions in Analysis Workspace, see [Preview dimensions](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md), [Break down dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md), and [Time-parting dimensions](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md).

## Add metrics to a project

[Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md) allow you to quantify data points in Analysis Workspace. They are most commonly used as columns in a visualization and tied to dimensions.

To add a metric to a project in Analysis Workspace:

1. Start adding a metric to your project in Analysis Workspace, as described in [Begin adding components to a project](#begin-adding-components-to-a-project).

1. Choose one of the following methods to add a metric in Analysis Workspace:

   * Drag a metric to the metric drop zone in an empty Freeform table to see that metric trended over the project's date period. 

     ![Add a metric to a project](assets/add-metrics.png)

   * Drag a metric when a dimension is present to see that metric compared to each dimension item. 

   * Drag a metric on top of an existing metric header to replace it.

   * Drag a metric next to a header to see both metrics side-by-side.

For more information about how to use metrics in Analysis Workspace, see [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

## Add segments to a project

[Segments](/help/components/segmentation/seg-overview.md) allow you to identify subsets of visitors based on characteristics or specific interactions.

You can use segments in Analysis Workspace in any of the following ways:

### Add segments to a panel

When you add segments to a panel, the segments apply to all content within the panel.

For information about how you can use the segment drop zone on a panel to filter your panel, see [Drop zone](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Panels overview](/help/analyze/analysis-workspace/c-panels/panels.md).

### Add segments to a column in a freeform table

When you add segments to a column in a freeform table, the segments apply to all content within the table column.

### Use segments when creating calculated metrics

In the Calculated metric builder, you can apply segments within your metric definition. 

For more information, see [Segmented metrics](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md).

## Add date ranges to a project

[Date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) determine the reporting time frame in Analysis Workspace, and can be applied to one or more panels within a project.

Each panel includes a date range by default. There are multiple ways to update a date range for a panel. One way to update a date range for a panel in Analysis Workspace is to drag a date range component from the left rail:

1. Start adding a date range to your project in Analysis Workspace, as described in [Begin adding components to a project](#begin-adding-components-to-a-project).

1. Drag a date range from the left rail onto the current date range in the upper-right portion of the panel.

     ![drop a date range](assets/daterange-drop.png)

For more information about how to use calendars and date ranges in Analysis Workspace, see [Calendar and date ranges overview](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).

-->