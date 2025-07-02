---
title: 注釈を表示
description: Analysis Workspaceで注釈を表示する方法。
role: User, Admin
feature: Annotations
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 84%

---

# 注釈を表示

注釈の表示方法は、表示場所と、1 日または日付範囲に及ぶかどうかに応じて、わずかに異なります。

## Workspaceで注釈を表示

| ビジュアライゼーションの<br/>タイプ | 説明 |
| --- | --- |
| **折れ線グラフの&#x200B;**<br/>**1 日** | 折れ線グラフのビジュアライゼーションで「![注釈](/help/assets/icons/Annotate.svg)」を選択すると、注釈の詳細を含むポップアップが表示されます。<br/>![1 日に注釈](assets/annotation-single-day.png)<br/>：[注釈ビルダー](create-annotations.md#annotation-builder)で注釈を編集するには、「![編集](/help/assets/icons/Edit.svg)」を選択します。注釈を削除するには、「![削除](/help/assets/icons/Delete.svg)」を選択します。 |
| **折れ線グラフの&#x200B;**<br/>**日付範囲** | 「![AnnotateRange](/help/assets/icons/AnnotateRange.svg)」を選択すると、注釈の詳細を含むポップアップと、日付範囲を示す折れ線グラフが下部に表示されます。<br/>![注釈範囲](assets/annotation-range.png)：[注釈ビルダー](create-annotations.md#annotation-builder)で注釈を編集するには、「![編集](/help/assets/icons/Edit.svg)」を選択します。注釈を削除するには、「![削除](/help/assets/icons/Delete.svg)」を選択します。 |
| **フリーフォームテーブル** | フリーフォームテーブルでは、ビジュアライゼーションの右上にある注釈ボタンからすべての注釈にアクセスできます。「![注釈](/help/assets/icons/Annotate.svg)」を選択して、すべての注釈の（スクロールリスト）を表示します。<br/>![注釈テーブル](assets/annotations-table.png)<br/>：注釈ごとに、「![編集](/help/assets/icons/Edit.svg)」を選択して[注釈ビルダー](create-annotations.md#annotation-builder)で注釈を編集し、「![削除](/help/assets/icons/Delete.svg)」を選択して注釈を削除できます。 |

{style="table-layout:auto"}

## PDF での注釈の表示

プロジェクトを PDF としてダウンロードするか、プロジェクトを PDF として送信すると、注釈は「注釈の概要」セクションに PDF で要約されます。

![注釈の説明を示す PDF ファイルのハイライト表示。](assets/annotations-pdf.png)


<!--
# View annotations

Annotations manifest slightly differently, depending on whether they span a single day or a date range.

## View annotations in Line charts or Tables

| Date | Appearance |
| --- | --- |
| **Single day** |   ![](assets/single-day.png)<p>When you hover over the annotation, you can see its details, you can edit it by selecting the pen icon, or you can delete it:<p> ![](assets/hover.png) |
| **Date range** |  The icon changes and when you hover over it, the date range appears.<p>![](assets/multi-day.png)<p>When you select it in the line chart, the annotation metadata appear, and you can edit or delete it:![](assets/multi-hover.png)<p>In a table, an icon appears on every date in the date range.<p>![](assets/multi-day-table.png)|
| **Overlapping annotations** | On days that have more than one annotation tied to them, the icon appears in a grey color.<p>![](assets/grey.png)<p>When you hover over the grey icon, all overlapping annotations appear:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## View annotations in a .pdf file

Since you cannot hover over icons in a .pdf file, this file (after export) provides notes of explanations at the bottom of a panel. Here is an example:

![](assets/ann-pdf.png)

## View annotations with non-trended data

Sometimes annotation are shown with non-trended data, but tied to a specific dimension. In that case, they appear only in a summary annotation in the bottom right corner. Here is an example:

![](assets/non-date.png)

The summary chart appears in all visualization types in the corner, not just in non-trended freeform tables and summary numbers. It also appears in visualizations like [!UICONTROL Donut], [!UICONTROL Flow],[!UICONTROL Fallout],[!UICONTROL Cohort], and so on.

![](assets/ann-summary.png)

-->