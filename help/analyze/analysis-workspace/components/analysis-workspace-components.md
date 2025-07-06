---
title: コンポーネントの概要
description: Adobe Analyticsが提供するコンポーネントの概要と、Analysis Workspaceでのコンポーネントの使用方法について説明します。
feature: Components
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 98%

---

# コンポーネントの概要

コンポーネントは、ビジュアライゼーション（フリーフォームテーブルなど）で使用したり、レポート機能を補完したりできる Adobe Analytics の機能です。

Adobe Analytics のメインインターフェイスからコンポーネントを管理するには、次の手順に従います。

1. 上部のバーから「**[!UICONTROL コンポーネント]**」を選択します。
1. 「**[!UICONTROL コンポーネント]**」を選択して、管理できるコンポーネントの概要を表示するか、メニューから管理するコンポーネントを直接選択します。

次のコンポーネントを管理できます。

* [セグメント](/help/components/segmentation/seg-home.md)：強力かつ焦点を絞ったオーディエンスセグメントを作成、管理、共有し、レポートに適用します。セグメントを使用すると、特性やインタラクションに基づいてユーザーのサブセットを特定できます。
* [計算指標](/help/components/c-calcmetrics/cm-overview.md)：レポートで使用する新しいコンポーネントとして指標と数式を使用します。
* [日付範囲](calendar-date-ranges/custom-date-ranges.md)：Analysis Workspace が提供する日付範囲をカスタマイズおよび調整します。
* [スケジュールされたプロジェクト](../curate-share/t-schedule-report.md)：スケジュールされたプロジェクトを管理します。
* [場所](../../../components/locations/locations-manager.md)：プロジェクトの書き出し先となる場所を管理します。
* [アラート](/help/components/c-alerts/intellligent-alerts.md)：アラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。
* [注釈](annotations/overview.md)：コンテキストデータのニュアンスとインサイトを組織に伝えます。
* [環境設定](/help/analyze/analysis-workspace/user-preferences.md)：Analysis Workspace の環境設定を管理します。



## Analysis Workspace のコンポーネント

Analysis Workspace のコンポーネントは、Workspace プロジェクトのパネルやビジュアライゼーションにドラッグ＆ドロップできる指標、ディメンション、セグメント、日付範囲で構成されています。計算指標やカスタム日付範囲など、作成するカスタムコンポーネントがこれらのパネルに追加されます。

コンポーネントパネルにアクセスするには、ボタンパネル内の![キュレート](/help/assets/icons/Curate.svg)／**[!UICONTROL コンポーネント]**&#x200B;を選択します。

![左パネルでコンポーネントアイコンをハイライト表示する Workspace パネル](assets/components.png)

プロジェクトでのコンポーネントの使用方法について詳しくは、[プロジェクトの作成](/help/analyze/analysis-workspace/home.md)を参照してください。


## コンポーネントの管理 {#actions}

Analysis Workspace の&#x200B;**[!UICONTROL コンポーネント]**&#x200B;メニューを使用して、新しいコンポーネントをすばやく作成できます。詳しくは、[Analysis Workspace メニュー](/help/analyze/analysis-workspace/home.md#menu)を参照してください。

コンポーネントを（個別に、または複数を選択して）管理できます。

1. 1 つまたは複数のコンポーネントを選択します。

1. コンテキストメニュー、または ![MoreVertical](/help/assets/icons/MoreVertical.svg) コンポーネントアクションボタン（コンポーネントの上部）から、次のいずれかのアクションを選択します。


   >[!TIP]
   >
   >複数のコンポーネントを選択するには、**[!UICONTROL Shift]** キーを押すか、**[!UICONTROL Command]** キー（macOS の場合）または **[!UICONTROL Ctrl]** キー（Windows の場合）を押します。


   ![タグ、お気に入り、承認、共有、削除を表示するコンポーネントアクションリスト。](assets/component-menu.png)

   | コンポーネントのアクション | 説明 |
   |--- |--- |
   | ![ラベル](/help/assets/icons/Label.svg)、[!UICONTROL **タグ**] | コンポーネントにタグを適用して整理したり管理したりします。次に、「![フィルター](/help/assets/icons/Filter.svg)」を選択するか、`#` を入力して、左パネルのタグで検索できます。タグは、コンポーネントマネージャーのフィルターとしても機能します。 |
   | ![星](/help/assets/icons/Star.svg)、[!UICONTROL **お気に入り**] | コンポーネントをお気に入りのリストに追加します。タグと同様に、左パネルのお気に入りで検索し、コンポーネントマネージャーでフィルタリングできます。 |
   | ![StarOutline](/help/assets/icons/StarOutline.svg)、**[!UICONTROL お気に入りを解除]** | コンポーネントをお気に入りのリストから削除します。 |
   | ![チェックマーク](/help/assets/icons/Checkmark.svg)、[!UICONTROL **承認**] | コンポーネントを「承認済み」とマークして、コンポーネントが組織で承認されていることをユーザーに知らせます。 タグと同様に、左パネルで「承認済み」で検索してフィルタリングできます。![チェックマーク](/help/assets/icons/Checkmark.svg)は、承認済みのコンポーネントを識別します。 |
   | ![共有](/help/assets/icons/ShareAlt.svg)、[!UICONTROL **共有**] | 組織内のユーザーとコンポーネントを共有します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |
   | ![削除](/help/assets/icons/Delete.svg)、[!UICONTROL **削除**] | 不要になったコンポーネントを削除します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |

カスタムコンポーネントは、それぞれのコンポーネントマネージャーを通じて管理することもできます。 例えば、[セグメントの管理](/help/components/segmentation/segmentation-workflow/seg-manage.md)を参照してください。

## コンポーネントリストの管理

Analysis Workspace の左パネルにあるコンポーネントリストを検索、フィルタリング、並べ替えると、特定のコンポーネントを見つけることができます。

### 検索

1. 左パネルで「**コンポーネント**」（![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)）を選択します。

2. 検索フィールドに、プロジェクトで使用するコンポーネントの名前を入力します。

   コンポーネントのタイプは、カラーとアイコンで識別されます。**ディメンション** ![ディメンションアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) はオレンジ色、**セグメント** ![セグメントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) は青色、**日付範囲** ![日付範囲アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) は紫色、**指標** ![指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) は緑色です。<br/>アドビアイコン（![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg)）は、計算指標テンプレートまたはセグメントテンプレートのいずれかを示します。電卓アイコン（![電卓アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)）は、組織の管理者が作成した計算指標を示します。

3. ドロップダウンメニューからコンポーネントを選択します。

### フィルター

1. 左パネルで&#x200B;**コンポーネント**&#x200B;アイコン（![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)）を選択します。

2. 「**フィルター**」、![データ辞書フィルターアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)を選択するか、検索フィールドに `#` を入力します。

3. 次のいずれかのフィルターオプションを選択して、コンポーネントのリストをフィルタリングします。

   | アイコン | フィルターオプション | 説明 |
   |---------|---|----------|
   | ![チェックマーク](/help/assets/icons/Checkmark.svg) | **[!UICONTROL 承認済み]** | 管理者が承認済みとしてマークしたコンポーネントのみを表示します。 |
   | ![星](/help/assets/icons/Star.svg) | **[!UICONTROL お気に入り]** | お気に入りのリストにあるコンポーネントのみを表示します。<br/>お気に入りのリストにコンポーネントを追加する方法について詳しくは、[コンポーネントの管理](#manage-components)を参照してください。 |
   | ![ディメンション](/help/assets/icons/Dimensions.svg) | **[!UICONTROL ディメンション]** | ディメンションであるコンポーネントのみを表示します。 |
   | ![イベント](/help/assets/icons/Event.svg) | **[!UICONTROL 指標]** | 指標であるコンポーネントのみを表示します。 |
   | ![セグメント化](/help/assets/icons/Segmentation.svg) | **[!UICONTROL セグメント]** | セグメントであるコンポーネントのみを表示します。 |
   | ![カレンダー](/help/assets/icons/Calendar.svg) | **[!UICONTROL 日付範囲]** | 日付範囲であるコンポーネントのみを表示します。 |
   | ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL *タグ名&#x200B;*]** | 特定のタグが選択されているコンポーネントのみを表示します。アドビテンプレートには専用のタグが使用できます。これは、アドビの[デフォルトの計算指標](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)です。 |

   フィルターで「![CrossSize75](/help/assets/icons/CrossSize75.svg)」を選択して、フィルターを削除します。

4. オプションで、[コンポーネントリストの並べ替え](#sort-the-component-list)の説明に従って、コンポーネントリストを並べ替えることができます。

### 並べ替え

<!-- {{release-limited-testing-section}}-->

1. （オプション）[コンポーネントリストのフィルタリング](#filter-the-component-list)で説明しているように、コンポーネントリストにフィルターを適用します。

2. 左パネルで「**コンポーネント**」（![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)）を選択します。

3. 「**並べ替え**」（![コンポーネントを並べ替えアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)）を選択し、次のフィルターオプションのいずれかを選択してコンポーネントのリストを並べ替えます。

次の並び替えオプションを使用できます。

{{components-sort-options}}

## アクセス権限

Analysis Workspace では、管理者はレポートでユーザーに公開するコンポーネントを[キュレート](/help/analyze/analysis-workspace/curate-share/curate.md)できます。


<!--
# Components overview

Components in Analysis Workspace consist of dimensions, metrics, segments, and date ranges that you can drag-and-drop onto a project. 

To access the Components menu, click the **[!UICONTROL Components]** icon in the left rail. You can switch among ![WebPage](/help/assets/icons/WebPage.svg)[panels](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html), [visualizations](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html), and components from the left rail icons or by using [hotkeys](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/component-overview.png)

You can also adjust the [View density settings](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) for the project to see more values in the left rail at once by going to **[!UICONTROL Project > Project Info & Settings > View Density]**.

## Dimensions {#dimensions}

[**Dimensions**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html) are text attributes that describe your visitor behavior and can be viewed, broken down, and compared in your analysis. They can be found in the left Component rail (orange section) and are typically applied as rows of a table. 

Examples of dimensions include [!UICONTROL Page Name], [!UICONTROL Marketing Channels], [!UICONTROL Device Type], and [!UICONTROL Products]. Dimensions are provided by Adobe and are captured through your custom implementation (eVar, Props, classifications, etc).

Each dimension also contains **dimension items** within it. Dimension items can be found in the left Component rail by clicking the right-arrow next to any dimension name (items are yellow).

Examples of dimension items include [!UICONTROL Homepage] (within the [!UICONTROL Page] dimension), [!UICONTROL Paid Search] (within the [!UICONTROL Marketing Channel] dimension), [!UICONTROL Tablet] (within the [!UICONTROL Mobile Device Type] dimension), and so on.

![](assets/dimensions.png)

## Metrics {#metrics}

[**Metrics**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html) are quantitative measures about visitor behavior. They can be found in the left Component rail (green section) and are typically applied as columns of a table.

Examples of metrics include [!UICONTROL Page views], [!UICONTROL Visits], [!UICONTROL Orders], [!UICONTROL Average Time spent], and [!UICONTROL Revenue/Order]. Metrics are provided by Adobe, or captured through your custom implementation ([!UICONTROL Success events]), or created using the [Calculated metric builder](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).

![](assets/metrics.png)

## Segments {#segments}

[**Segments**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html) are audience filters that are applied to your analysis. They can be found in the left Component rail (blue section) and are typically applied at the top of a panel or above metric columns in a table. 

Examples of segments include [!UICONTROL Mobile Device Visitors], [!UICONTROL Visits from Email], and [!UICONTROL Authenticated Hits]. Segments are provided by Adobe, or created in the [panel dropzone](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html), or created using the [Segment builder](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html).

![](assets/segments.png)

## Date Ranges {#date-ranges}

[**Date Ranges**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) are the range of dates you conduct your analysis across. They can be found in the left Component rail (purple section) and are typically applied in the calendar of each panel.

You can make the date range components relative to the panel calendar. For additional information, see [About relative panel date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates).

Examples of date ranges include July 2019, [!UICONTROL Last 4 weeks], and [!UICONTROL This month]. Date ranges are provided by Adobe, applied in the [panel calendar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html), or created using the [Date range builder](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html).

![](assets/date-ranges.png)


## Manage components {#actions}

You can manage components directly in the left rail. 

1. Right-click a component.

   Or
   
   Select a component, then select the **Action** (3-dot) icon at the top of the component list.

   >[!TIP]
   >
   >   You can select multiple components by holding Shift, or by holding Command (on Mac) or Ctrl (on Windows).


   ![](assets/component-actions.png)

   | Component action | Description |
   |--- |--- |
   | [!UICONTROL **Tag**] | Organize or manage components by applying tags to them. You can then search by tag in the left rail by clicking the filter or typing #. Tags also act as filters in the component managers. |
   | [!UICONTROL **Favorite**] | Add the component to your list of favorites. Like tags, you can search by Favorites in the left rail and filter by them in the component managers. |
   | [!UICONTROL **Approve**] | Mark components as Approved to signal to your users that the component is organization-approved. Like tags, you can search by Approved in the left rail and filter by them in the component managers. |
   | [!UICONTROL **Share**] | Share components to users in your organization. This option is available for custom components only, such as segments or calculated metrics. |
   | [!UICONTROL **Delete**] | Delete components that you no longer need. This option is available for custom components only, such as segments or calculated metrics. |

Custom components can also be managed through their respective Component managers. For example, the [Segment Manager](/help/components/segmentation/segmentation-workflow/seg-manage.md).

## Search, filter, and sort the component list

You can search, filter, and sort the component list in the left rail of Analysis Workspace to quickly locate a particular component. 

### Search the component list

1. Select the **Components** icon ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left rail.

2. In the search field, begin typing the name of the component you want to use in your project.

   The type of component can be identified by both color and icon. **Dimensions** ![Dimension icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) are orange, **Segments** ![Segment icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) are blue, **Date ranges** ![Date range icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) are purple, and **Metrics** ![Metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) are green. The Adobe icon indicates either a calculated metric template or a segment template, and the calculator icon ![Calculator icon](assets/calculated-metric-icon-created.png) indicated a calculated metric that was created by an Analytics administrator in your organization. 

3. Select the component when it appears in the drop-down list.

### Filter the component list

1. Select the **Components** icon ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left rail.

2. Select the **Filter** icon ![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg).

   Or

   Type the pound sign (#) in the search field.

3. Select any of the following filter options to filter the list of components:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | Show only components that are marked as Approved by an administrator. |
   | [!UICONTROL **Favorites**] | Show only components that are in your list of Favorites. For information about adding components to your list of favorites, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensions**] | Show only components that are Dimensions. |
   | [!UICONTROL **Metrics**] | Show only components that are Metrics. |
   | [!UICONTROL **Segments**] | Show only components that are Segments.  |
   | [!UICONTROL **Date ranges**] | Show only components that are Date Ranges. |
   | [!UICONTROL **Show all**] | Show all components. This option is available only for administrators. |
   | [!UICONTROL **Unapproved**] | Show only components that are not yet marked as Approved by an administrator. As an administrator, this is helpful when identifying components that require your review and approval. This option is available only for administrators. |

4. (Optional) To further hone the list, you can sort the component list, as described in [Sort the component list](#sort-the-component-list).

### Sort the component list

1. (Optional) Apply any filters to the component list, as described in [Filter the component list](#filter-the-component-list).

2. Select the **Components** icon ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) in the left rail.

3. Select the **Sort** icon ![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), then select any of the following filter options to sort the list of components:

   {{components-sort-options}}

-->