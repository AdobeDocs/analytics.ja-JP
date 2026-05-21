---
title: Report Builderでのデータブロックの管理
description: Report Builderでデータブロックを管理する方法について説明します。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
TQID: https://experienceleague.adobe.com/ABoNikHpWClofkV4y5i0z39aDZeWd5nmCz3tcVFoOMY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 519
ht-degree: 21%

---

# データブロックの管理

[!UICONTROL &#x200B; データブロックマネージャー]を使用して、ブック内のすべてのデータブロックを表示および管理できます。 [!UICONTROL &#x200B; データブロックマネージャー]には、特定のデータブロックを検索できる検索、フィルター、並べ替え機能が用意されています。 1 つまたは複数のデータブロックを選択した後、選択したデータブロックを編集、削除、または更新できます。

## データブロックを表示

ブック内のすべてのデータブロックをリストするテーブルを表示するには、![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**&#x200B;を選択します。

![すべてのデータブロックのリストを表示する管理オプション。](./assets/image53.png){zoomable="yes"}

**[!UICONTROL データブロックマネージャー]**&#x200B;には、ワークブック内に存在するすべてのデータブロックを含むテーブルが表示されます。

![&#x200B; ブック内に存在するすべてのデータブロックのリスト。](./assets/image52.png){zoomable="yes"}

![ColumnSetting](/help/assets/icons/ColumnSetting.svg)を使用して、表示する列を選択できます。

## データブロックの並べ替え

表示されている列でデータブロックテーブルをソートできます。 例えば、レポートスイート、セグメント、日付範囲などの変数ごとにデータブロックを並べ替えることができます。

データブロックテーブルを並べ替えるには、列見出しを選択します。 同じ列見出しを選択して、並べ替え順序を反転します。


## データブロックを検索

![検索](/help/assets/icons/Search.svg) **[!UICONTROL _検索_]** フィールドを使用して、データブロックテーブル内の任意の項目を検索します。 例えば、データブロックやレポートスイートに含まれている指標を検索できます。 また、日付範囲、変更日または最終実行日の列に表示される日付を検索することもできます。


## データブロックを編集

データブロックのレポートスイートと日付範囲を編集できます。 データブロックに適用されたセグメントがあります。

例えば、既存のセグメントを1つ以上のデータブロック内の新しいセグメントに置き換えることができます。

1. 更新するデータブロックを選択します。 最上位のチェックボックスを選択してすべてのデータブロックを選択するか、個々のデータブロックを選択できます。

   ![鉛筆の編集アイコン &#x200B;](./assets/image56.png){zoomable="yes"}

1. ![編集](/help/assets/icons/Edit.svg)を選択して、**[!UICONTROL クイック編集]** ウィンドウを表示します。

   ![&#x200B; クイック編集ウィンドウ &#x200B;](./assets/image58.png){zoomable="yes"}

1. レポートスイート、日付範囲、またはセグメントを更新するリンクを選択します。 **[!UICONTROL クイック編集]** - **[!UICONTROL セグメント]**&#x200B;では、選択したデータブロックのセグメントを追加、削除、または更新できます。

   ![&#x200B; クイック編集ウィンドウの「セグメントを追加」フィールド &#x200B;](./assets/image59.png){zoomable="yes"}

## データブロックを更新

「![更新](/help/assets/icons/Refresh.svg)」を選択して、データブロックテーブルを更新します。

データブロックが更新されているかどうかを確認するには、更新ステータスアイコンを表示します。

- データ ブロックが正常に更新されると、![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg)が表示されます。

- 更新に失敗したデータブロックには、![AlertRed](/help/assets/icons/AlertRed.svg)が表示されます。


## データブロックを削除

1つ以上のデータブロックを削除するには：

1. 1つ以上のデータブロックを選択します。
1. 「![削除](/help/assets/icons/Delete.svg)」を選択します。
1. **[!UICONTROL データブロックを削除]** ダイアログで&#x200B;**[!UICONTROL 削除]**&#x200B;を選択するか、**[!UICONTROL キャンセル]**&#x200B;を選択して削除をキャンセルします。

## データブロックをグループ化

データブロックは、**[!UICONTROL 別にグループ化]** ドロップダウンメニューを使用してグループ化するか、列タイトルを選択できます。

列ごとにデータブロックを並べ替えるには、列タイトルを選択します。 データブロックをグループ別にグループ化するには、**[!UICONTROL グループ化の条件]**&#x200B;ドロップダウンメニューからグループ名を選択します。 例えば、以下のスクリーンショットは、レポートスイート別にグループ化されたデータブロックを示しています。

グループ化を使用すると、セグメントなどの共通エレメントを変更するデータブロックをすばやく選択できます。

![&#x200B; シート別グループ リストを表示するデータ ブロック マネージャー。](./assets/group-data-blocks.png){zoomable="yes"}



<!--

# Manage Data Blocks in Report Builder

You can view and manage all data blocks in a workbook using the Data Block Manager. The Data Block Manager provides search, filter, and sort capabilities that allow you to quickly locate specific data blocks. After selecting one or more data blocks, you can edit, delete, or refresh the selected data blocks.

![The Data block manager screen.](./assets/image52.png)

## View Data Blocks

Click **Manage** to view a list of all data blocks in a workbook.

![The Manage option to view a list of all data blocks.](./assets/image53.png)

The Data Block Manager lists all data blocks present in a workbook. 

## Sort the Data Blocks list

You can sort the data block list by a displayed column. For example, you can sort the data block list by report suites, segments, date range, and other variables.

To sort the data block list, click a column heading.

![Sorting the data blocks.](./assets/image54.png)

## Search the Data Block list

Use the Search field to locate anything in the data block table. For example, you could search for metrics contained in the data blocks or report suite. You can also search for dates appearing in the date range, date modified, or last run date columns.

![Using the Search field to locate anything in the data block table.](./assets/image55.png)

## Edit Data Blocks

You can edit the report suite, date range, or the segments applied to one or more data blocks.

For example, you can replace an existing segment with a new segment in one or more data blocks.

1. Select the data blocks that you want to update. You can select the top-level check box to select all data blocks or you can select individual data blocks.

   ![The pencil edit icon](./assets/image56.png)

1. Click the edit icon to display the Quick edit window.

   ![The Quick edit window](./assets/image58.png)

1. Select a segment link to update report suites, date ranges, or segments.

   ![The Add Segment field in the Quick edit window](./assets/image59.png)

## Refresh Data Blocks

Click the refresh icon to refresh the data blocks in the list.

<img src="./assets/refresh-icon.png" width="15%" alt="Refresh icon"/>

To verify if a data block is refreshed, view the refresh status icon. 

A successfully refreshed data block displays a checkmark in a green circle: <img src="./assets/refresh-success.png" width="5%" alt="Green circle with check mark icon"/>. 

A data block that has failed to refresh displays a warning icon: <img src="./assets/refresh-failure.png" width="5%" alt="Red triangle with exclamation mark icon"/>.This makes it easy to identify if any data blocks have errors.


![Data block manager showing refresh status for each data block listed.](./assets/image512.png)

## Delete a Data Block

1. Select a data block in the Data Block manager. 
1. Click the trash can icon to delete the selected data block.

## Group Data Blocks

You can group data blocks using the **Group by** drop-down menu or you can click a column title. To sort data blocks by column, click the column title. To group data blocks by groups, select a group name from the **Group by** drop-down menu. For example, the screenshot below shows data blocks grouped by Sheet. It shows data blocks grouped by Sheet1 and Sheet2.  This is useful, for example, in the segment-replacing use case. If you have multiple segments applied to each data block, it is helpful to create a group containing all the data blocks that you want to replace. Then you can easily select and edit them all at once.

![Data block manager showing the Group by Sheet list.](./assets/group-data-blocks.png)

## Modify the Data Block Manager view

You can modify which columns are visible in the Data Block Manager window.


Click the column list <img src="./assets/image515.png" width="3%" alt="Column list icon"/> icon to select which columns are listed in the Data Block Manager. Select a column name to display the column. Deselect the column name to remove the column from view.

![Data block manager showing the column list](./assets/image516.png)

-->