---
description: 組織全体の予定レポートを表示および管理します。
title: スケジュール済みプロジェクトマネージャー
feature: Admin Tools
exl-id: 8bc8d983-f680-48fa-8483-694c87a9ae4c
source-git-commit: d4d0eeac4f1f29e4c68e80b6fa0fe987a1fb32b9
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 42%

---

# スケジュールされたプロジェクト

スケジュールされたAnalysis Workspace プロジェクトは、**[!UICONTROL コンポーネント]**/**[!UICONTROL スケジュールされたプロジェクト]** を使用して、Adobe Analyticsで管理できます。

**[!UICONTROL スケジュールされたプロジェクト]** では、繰り返しプロジェクトスケジュールを編集および削除できます。  [ スケジュール済みプロジェクトリスト ](#scheduled-project-list) には、特定のユーザーが作成した項目が表示されます。 アプリケーションでユーザーアカウントが無効になっている場合、スケジュールされたすべての配信が停止します。

![ スケジュールされたプロジェクトインターフェイス ](assets/scheduled-projects.png)

## スケジュール済みプロジェクトリスト

「スケジュール済みプロジェクト」リスト ➊ は、次の列が表示されます。

| 列 | 説明 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | スケジュールされたプロジェクトを 1 つ以上選択すると、スケジュールされたプロジェクト インターフェイスの下部に青いアクションバーが表示されます。 詳しくは、[アクション](#actions)を参照してください。 |
| ![星](/help/assets/icons/Star.svg) | スケジュールされたプロジェクトを ![ 星 ](/help/assets/icons/Star.svg) にするか、![ 星の概要 ](/help/assets/icons/StarOutline.svg) にするかを選択します。 |
| **[!UICONTROL スケジュール ID]** | 主にデバッグ目的で使用される ID。 |
| **[!UICONTROL 名前]** | このプロジェクトの名前。<br/>![InfoOutline](/help/assets/icons/InfoOutline.svg) を選択すると、スケジュールされたプロジェクトの詳細が表示されます。<br/> 詳細 ![ を選択して ](/help/assets/icons/More.svg) コンテキストメニューを開きます。 このメニューから、次の操作を実行できます。<ul><li>![ 削除 ](/help/assets/icons/Delete.svg)**[!UICONTROL 削除]** スケジュールされたプロジェクト。</li><li>![ ラベル ](/help/assets/icons/Labels.svg)**[!UICONTROL タグ付け]** スケジュールされたプロジェクト。</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)**[!UICONTROL Approve]** スケジュールされたプロジェクト。</li><li>![FileCSV](/help/assets/icons/FileCSV.svg)**[!UICONTROL Export CSV]**：スケジュールされたプロジェクトを CSV ファイルに書き出します。</li></ul> |
| **[!UICONTROL 所有者]** | プロジェクトを作成し所有しているユーザー。 |
| **[!UICONTROL タグ]** | （任意）タグ付けは、プロジェクトを整理するのに適した方法です。すべてのユーザーがタグを作成し、1 つ以上のタグをプロジェクトに適用できます。ただし、タグを表示できるのは、自分が所有しているプロジェクトか、自分と共有されているプロジェクトに限られます。 |
| **[!UICONTROL 配信先]** | スケジュールされたプロジェクトの受信者。 |
| **[!UICONTROL 有効期限]** | スケジュールの頻度に関係なく、有効期限を最大 1 年まで設定できます。 |
| **[!UICONTROL 頻度]** | このスケジュールプロジェクトを 1 人または複数の受信者に送信する頻度。 |
| **[!UICONTROL 実行時刻]** | このスケジュールされたプロジェクトが送信される時刻。 |
| **[!UICONTROL クエリ数]** | このプロジェクトに対するクエリの数。 |
| **[!UICONTROL 最長の日付範囲]** | スケジュールされたプロジェクトに定義されている最長の日付範囲。 この値は、パフォーマンスの問題の調査に関連する可能性があります。 詳しくは、[ レポートアクティビティマネージャー ](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) を参照してください。 |
| **[!UICONTROL クエリ数]** | スケジュールされたプロジェクトで実行されたクエリの数。 この値は、パフォーマンスの問題の調査に関連する可能性があります。 詳しくは、[ レポートアクティビティマネージャー ](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) を参照してください。 |


![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を構成できます。

![ 検索 ](/help/assets/icons/Search.svg) を使用して、スケジュールされたプロジェクトを検索します。 また、フィルターパネルからフィルターが適用されているかどうかを確認することもできます。 フィルターを削除するには、フィルターに ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択します。 すべてのフィルターを削除するには、「**[!UICONTROL すべてクリア]**」を選択します。

スケジュールされたプロジェクトを編集するには、スケジュールされたプロジェクトのタイトルを選択します。 **[!UICONTROL スケジュールされたプロジェクトを編集]** ダイアログを使用して、スケジュールの詳細を更新します。 詳しくは [ その他へのファイルの送信 ](../analyze/analysis-workspace/curate-share/t-schedule-report.md) を参照してください。

![ スケジュールされたプロジェクトを編集 ](assets/edit-scheduled-project.png)

「**[!UICONTROL 更新]**」を選択して、スケジュールを更新します。




## アクション

スケジュール済みプロジェクトマネージャーでの一般的な操作は次のとおりです。1 つ以上のスケジュールされたプロジェクトを選択する際に、コンテキストメニューまたは青いアクションバーからアクションを選択できます。

| アイコン | アクション | 説明 |
|:---:|---|---|
| ![閉じる](/help/assets/icons/Close.svg) | **[!UICONTROL *x *個を選択済み]** | 「」を選択すると、選択したスケジュールされたプロジェクトの選択を解除できます。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | プロジェクト用に選択したスケジュール済みプロジェクトを削除します。プロジェクトは削除されません。 |
| ![ラベル](/help/assets/icons/Labels.svg) | **[!UICONTROL タグ]** | 選択したスケジュール済みプロジェクトにタグ付けします。 **[!UICONTROL スケジュールされたプロジェクトにタグ付け]** で、タグを選択し、「**[!UICONTROL 保存]**」を選択して保存します。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 承認]** | 選択したスケジュールされたプロジェクトを承認します。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV に書き出し]** | 選択したスケジュールされたプロジェクトを `Export Scheduled Projects List.csv` という名前のファイルにエクスポートします。 |


## フィルター

フィルターパネル ➌ ールを使用して、スケジュールされたプロジェクト [ スケジュールされたプロジェクト リスト ](#scheduled-project-list) をフィルタリングできます。 フィルターパネルを表示または非表示にするには、![フィルター](/help/assets/icons/Filter.svg) を使用します。

フィルターパネルは、次のセクションで構成されています。

### タグ

| タグ | 説明 |
|---|---|
| ![タグ](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | 「**[!UICONTROL タグ]**」セクションでは、タグでフィルタリングできます。 <ul><li>フィルタリングに使用するタグを検索するには、![検索](/help/assets/icons/Search.svg) **[!UICONTROL タグを検索]**&#x200B;を使用します。</li><li>複数のタグを選択できます。使用できるタグは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>7︎⃣：特定のタグに関連付けられているスケジュールされたプロジェクトの数。</li></ul></li></ul> |


### 所有者

| 所有者 | 説明 |
|---|---|
| ![所有者](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | 「**[!UICONTROL 所有者]**」セクションでは、所有者でフィルタリングできます。 <ul><li>フィルタリングに使用する所有者を検索するには、![検索](/help/assets/icons/Search.svg) *所有者を検索*&#x200B;を使用します。</li><li>複数の所有者を選択できます。使用できる所有者は、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>4︎⃣：特定の所有者に関連付けられているスケジュールされたプロジェクトの数。</li></ul></li></ul> |


### その他のフィルター

| その他のフィルター | 説明 |
|---|---|
| ![その他のフィルター](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | 「**[!UICONTROL その他のフィルター]**」セクションでは、他の定義済みフィルターでフィルタリングできます。<ul><li>次のオプションから 1 つ以上を選択できます。<ul><li> **[!UICONTROL 期限切れ]**：期限切れのスケジュール済みプロジェクトをフィルタリングします。</li><li>**[!UICONTROL 失敗]**: スケジュールが失敗した、スケジュールされたプロジェクトをフィルタリングします。</li></ul>選択できる内容は、役割と権限によって異なります。</li><li>複数のフィルターを選択できます。使用できるその他のフィルターは、フィルターパネルの他のセクションでの選択によって異なります。</li><li>数値は次の内容を示します。<ul><li>4︎⃣：特定の他のフィルターに関連付けられているスケジュールされたプロジェクトの数。</li></ul></li></ul> |


<!--
# Scheduled projects

Scheduled Analysis Workspace projects can be managed under **Analytics > Components > Scheduled Projects**.

When you manage scheduled projects, you can edit and delete recurring project schedules:

*  Change the file type (.csv or PDF)
*  Update the project description
*  Add or remove recipients
*  Change the frequency

To modify a scheduled project

1.  Select **Analytics > Components > Scheduled Projects**.
1.  Search for a schedule in the search bar or by using the filter options in the left rail. You can filter by [!UICONTROL Tags], [!UICONTROL Owners], [!UICONTROL Favorites], and more.

![Screenshot showing the scheduled projects list with the column displaying title, owner, tags, delivered to, and other columns described in the Available columns section.](assets/scheduled-project-manager2.png)

## Available columns

| Field | Description |
| --- | --- |
| [!UICONTROL Favorites] | Selecting the star icon makes this schedule a favorite. |
| [!UICONTROL Schedule ID] | This ID is used mainly for debugging purposes. |
| [!UICONTROL Title and description] | Title and description of this project. |
| [!UICONTROL Owner] | The person who created and owns the project. |
| [!UICONTROL Tags] | (optional) Tagging is a good way to organize projects. All users can create tags and apply one or more tags to a project. However, you can see tags only for those projects that you own or that have been shared with you.  |
| [!UICONTROL Delivered to] | The recipient(s) of this scheduled project. |
| [!UICONTROL Expiration date] | For any scheduled project frequency, you can set the expiration date for up to one year in the future. |
| [!UICONTROL Frequency] | How often you want to have this schedule project sent to the recipient(s). |
| [!UICONTROL Execution time] | At what time of day this scheduled project gets sent. |
| [!UICONTROL Number of queries] | The number of queries against this project. | 

## Common actions

The following are common actions in the Scheduled Projects manager:

|Action|Description|
|---|---|
|**[!UICONTROL Edit]**|Select the title of the schedule to update its delivery settings.|
|**[!UICONTROL Delete]**|Select the scheduled project in the list and then click Delete from the menu. This will delete the selected schedule for the project; the project itself will not be deleted.|
|**[!UICONTROL Tag]**|Select the scheduled project in the list and then choose "Tag" or "Approve" to organize your schedules and make them easier to search for.|
|**[!UICONTROL View failed schedules]**|Navigate to the left rail > Other filters > Failed to see schedules that have failed.|
|**[!UICONTROL View expired schedules]**|Navigate to the left rail > Other filters > Expired to see schedules that have expired. Click the title of the schedule to setup a new delivery schedule.|
|**[!UICONTROL View schedule ID]**|Navigate to column options in the top right and add the Schedule ID column to the table. The scheduled ID is often useful for debugging.|

The Scheduled Projects manager shows the items that a specific user created. If the user account is disabled in the application, all scheduled deliveries stop. Scheduled project ownership can be transferred to a new user under **Admin** > **Analytics Users & Assets** > **Transfer Assets**.
-->