---
title: 注釈を管理
description: Analysis Workspaceで注釈を管理する方法を説明します。
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 88%

---

# 注釈を管理

一元的な[!UICONTROL 注釈]管理インターフェイスから、共有、フィルター、タグ付け、承認、コピー、削除および注釈をお気に入りとしてマークできます。注釈を管理するには、以下の手順に従います。

* メインインターフェイスで「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL 注釈]**」を選択します。


>[!NOTE]
>
>特定の Workspace プロジェクト内で作成した注釈は、すべてのプロジェクトで注釈を使用できるように設定していない限り、[!UICONTROL 注釈]マネージャーに表示されません。
>

## 注釈マネージャー

注釈マネージャーには、次のインターフェイス要素があります。

![注釈インターフェイス](assets/annotations-manager.png)

### 注釈リスト

注釈リスト ➊ には、所有するすべての注釈、すべてのプロジェクトを対象とした注釈、自分と共有されている注釈が表示されます。 リストには、次の列があります。

| 列 | 説明 |
| --- | --- |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 注釈「![星](/help/assets/icons/Star.svg)」を優先するか、「![StarOutline](/help/assets/icons/StarOutline.svg)」を優先しないかを選択します。 |
| **[!UICONTROL タイトルと説明]** | 注釈ビルダーで提供されます。タイトルと説明を編集するには、タイトルリンクを選択して[注釈ビルダー](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder)を開きます。共有注釈には、「![共有](/help/assets/icons/ShareAlt.svg)」と表示されます。 |
| **[!UICONTROL レポートスイート]** | この注釈が適用されるレポートスイート。 |
| **[!UICONTROL 所有者]** | 注釈の所有者。ユーザーには、自分が所有している注釈または自分と共有されている注釈のみが表示されます。 |
| **[!UICONTROL 適用された日付範囲]** | この注釈が適用される日付または日付範囲。 |
| **[!UICONTROL タグ]** | この注釈のタグ。 |
| **[!UICONTROL 共有先]** | 注釈を共有した個人またはグループ。選択して、**[!UICONTROL コンポーネントを共有]**&#x200B;ダイアログを開きます。 |
| **[!UICONTROL 変更日時]** | 注釈が最後に変更された日時を表示します。 |

{style="table-layout:auto"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

注釈に対するアクションは、アクションバーの ➋ を使用して実行できます。 アクションバーには、次のアクションが含まれます。

| アイコン | アクション | 説明 |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 追加]** | [注釈ビルダー](create-annotations.md#annotation-builder)を使用して、別の注釈を追加します。 |
| ![検索](/help/assets/icons/Search.svg) | [!UICONTROL *タイトルで検索*] | リストで注釈が選択されていない場合は、この検索フィールドを使用して注釈を検索します。 |
| ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL タグ]** | 選択した注釈にタグを付けます。**[!UICONTROL タグコンポーネント]**&#x200B;ダイアログで、選択した注釈のタグを選択または選択解除します。「**[!UICONTROL 保存]**」を選択して、選択した注釈のタグを保存します。 |
| ![共有](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共有]** | 選択した注釈を共有します。**[!UICONTROL コンポーネントを共有]**&#x200B;ダイアログでは、「![検索](/help/assets/icons/Search.svg)「」、「*個人またはグループを検索*」、または「**[!UICONTROL 組織]**」または「**[!UICONTROL グループ]**」を選択できます。「**[!UICONTROL 保存]**」を選択して、選択した注釈の共有の詳細を保存します。詳しくは、[注釈の共有](#share-annotations)を参照してください。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 選択した注釈を削除します。確認メッセージが表示されます。 |
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 名前変更]** | 選択した 1 つの注釈の名前を変更します。選択すると、注釈の名前をインラインで変更できます。 |
| ![コピー](/help/assets/icons/Copy.svg) | **[!UICONTROL コピー]** | 選択した注釈をコピーします。同じ名前とサフィックスを持つ新しい注釈が作成されます（コピー） |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV に書き出し]** | 注釈を `Annotations List.csv` ファイルに書き出します。 |

### アクティブなフィルターバー

フィルターバーの ➌ には、アクティブなフィルター（存在する場合）が表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。複数のフィルターを指定した場合は、「**[!UICONTROL すべて削除]**」を使用すると、すべてのフィルターを削除できます。

### フィルターパネル

注釈は、左側のパネルの **[!UICONTROL 「]** フィルター ➍」を使用してフィルタリングできます。 フィルターパネルには、フィルターのタイプと、フィルタリングを行う注釈の数が表示されます。「![フィルター](/help/assets/icons/Filter.svg)」を選択して、フィルターパネルの表示を切り替えます。

フィルターリストをフィルタリングするには、次の手順に従います。

1. 「![フィルター](/help/assets/icons/Filter.svg)」を選択して、フィルターパネルを開きます。フィルターリストにスペースが必要な場合は、もう一度「![フィルター](/help/assets/icons/Filter.svg)」を選択してパネルを閉じることができます。
1. 使用可能な任意の[フィルターセクション](#filter-sections)を使用して、注釈をフィルタリングできます。

   >[!INFO]
   >
   >*項目*&#x200B;とは、[注釈リスト](manage-annotations.md#annotations-list)に表示される注釈項目を指します。
   > 

#### フィルターセクション

{{tagfiltersection}}
{{reportsuitefiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


[注釈リスト](manage-annotations.md#annotations-list)は、フィルター設定に基づいて自動的に更新されます。設定済みのフィルターは、[アクティブなフィルターバー](manage-annotations.md#active-filter-bar)で確認できます。


## 注釈を編集

次の 2 つの方法で注釈を編集できます。

* Workspace プロジェクトでは、[コンポーネント情報](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info)アイコンを使用します。

* [[!UICONTROL 注釈]リスト](#annotations-list)で、注釈のタイトルを選択します。

注釈を編集するには、[注釈ビルダー](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder)を使用します。

## 注釈の共有

注釈を共有する場合や、自分と共有されている注釈を操作する場合は、次が適用されます。

* 他のユーザーと共有するプロジェクト内のプロジェクト専用の注釈は、それらのユーザーに対して表示されます。ユーザーは、これらのプロジェクト専用の注釈を編集または削除できません。
* 注釈を保存してその注釈をユーザーと直接共有する場合、そのユーザーは、管理者権限を持っている場合にのみ、注釈を編集および削除できます。

* プロジェクトが共有されている場合、そのプロジェクトで作成された注釈は、そのプロジェクトでのみ表示されます。注釈が直接共有されている場合、その注釈は、その注釈を表示できるすべてのプロジェクトに表示されます。

## 注釈とタイムゾーン

すべての注釈は、タイムスタンプと共に作成されますが、「時間」や「タイムゾーン」の情報は含まれません。レポート時には、パネル用に設定されたレポートスイートのタイムゾーンが使用されます。


<!--
# Manage annotations

The [!UICONTROL Annotations manager] shows you all of the annotations that you own or that have been shared with you. Project-specific annotations do not appear here. You can use this interface to share, filter, tag, copy, delete, and favorite your annotations. Administrators can manage and approve annotations.

**[!UICONTROL Components]** > **[!UICONTROL Annotations]**

## Annotations Manager user interface

![](assets/annotation-mgr.png)

| UI Element | Description |
| --- | --- |
| [!UICONTROL Title and Description] | Provided in the Annotations Builder. To edit the title and description, click the title link - this takes you back to the Annotations Builder.  |
| [!UICONTROL Report Suite] | The report suites that this annotation applies to.  |
| [!UICONTROL Owner] | Indicates who owns the annotation. As a non-Admin, you can see only annotations that you own or those that were shared with you. |
| [!UICONTROL Applied Date Range] | The date or date range that this annotation applies to. |
| [!UICONTROL Shared with] | Lists how many individuals or groups that you shared the annotation with. Click for more detail. |
| [!UICONTROL Date Modified] | Shows the date and time that the annotation was last modified. |

{style="table-layout:auto"}

## Edit annotations

Editing an annotation means that you can adjust date ranges, colors, scope, or whether it applies to all report suites or projects. You can edit annotations in two ways:

* In a line chart, hover over the annotation and click the pencil icon within the popover.
* In the [!UICONTROL Annotations Manager], click the title of the annotation.

Both of these options land you back in the [!UICONTROL Annotations Builder]. There, you can make the necessary adjustments and save the new version.

## Share annotations

When sharing annotations or working with annotations that were shared with you, keep this in mind:

* If you create a project with project-only annotations, then share the project with another user, annotations cannot be edited or deleted by anyone that you share the project with.
* If you save an annotation and share it directly with a user, they can edit/delete the annotation only if they have admin rights.
* If a project is shared with you with a project-only annotation, it shows up only in that project. If the annotation is shared directly with you, it shows up in all projects where that annotation can be displayed. 

## Annotations and time zones

All annotations are created with a timestamp, but no hours or timezone information. At report time, the timezone of the panel's report suite is always applied. For example, an annotation created for Christmas Day happens on December 25 no matter what report suite timezone you are in. 

## Other annotation tasks

The Annotations manager lets Administrators edit, add, tag, delete, rename, approve, copy, export, and filter annotations. It is not visible to non-Admin users. 

Additional options are available when you select at least one annotation:

| Task | Description |
| --- | --- |
| [!UICONTROL Add] | Takes you to the Annotations builder where you can create annotations. |
| [!UICONTROL Tag] | All users can create tags for annotations and apply one or more tags to an annotation. However, you can see tags only for annotations that you own. |
| [!UICONTROL Delete] | Deleting an annotation removes it from any project in your organization. |
| [!UICONTROL Rename] | Renaming an annotation renames it in all projects that it was applied to. |
| [!UICONTROL Copy] | Creates a distinct copy with its own annotation ID, but with the same name and definition.|
| [!UICONTROL Export to CSV] | Export the annotation definition to a .csv file.|
| [!UICONTROL Filter] (left rail) | Filter by tags, report suite, owners, and other filters (Mine, Approved, Favorites, Shared with me, and Show All).|

{style="table-layout:auto"}

-->