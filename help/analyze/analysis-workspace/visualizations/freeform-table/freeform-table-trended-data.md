---
description: Analysis Workspaceでフリーフォームテーブルのトレンドデータを表示する方法を説明します。
title: フリーフォームテーブルのトレンドデータの表示
feature: Freeform Tables
role: User, Admin
source-git-commit: 9035ea758a5e84812460c042685eae954303cc8a
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# フリーフォームテーブルのトレンドデータの表示

フリーフォームテーブルに含まれるデータのトレンドを表示できます。 このトレンドデータは、Analysis Workspace内の次の領域に表示されます。

* [スパークライン](#use-sparklines-to-view-trended-data)

* [線のビジュアライゼーション](#use-line-visualizations-to-view-trended-data)

## スパークラインを使用したトレンドデータの表示

スパークラインは、フリーフォームテーブルの指標列ヘッダーに表示されます。

![&#x200B; フリーフォームテーブルのスパークライン &#x200B;](assets/table-sparkline.png)

スパークラインには常に以下が含まれます。

* 列内のすべてのデータのトレンドデータ

* テーブルディメンションに適用される検索フィルター条件

  詳しくは、「[&#x200B; フィルターと並べ替え &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)」を参照してください。

## 折れ線グラフのビジュアライゼーションを使用したトレンドデータの表示

[&#x200B; 折れ線グラフ &#x200B;](/help/analyze/analysis-workspace/visualizations/line.md) ビジュアライゼーションには、接続先のフリーフォームテーブルのデータが表示されます。

### 線のビジュアライゼーションのフリーフォームテーブルへの接続

折れ線グラフのビジュアライゼーションがプロジェクトに追加された方法とタイミングによっては、目的のフリーフォームテーブルに既に接続されている場合があります。 を確認するか、手動で接続するには、次の手順を使用します。

1. Analysis Workspace プロジェクトに線のビジュアライゼーションを追加します。

1. ビジュアライゼーション名の横にある点を選択し、「**[!UICONTROL データソース]**」タブを選択した後、折れ線グラフビジュアライゼーションに接続するフリーフォームテーブルの名前を選択します。

   ![&#x200B; フリーフォームテーブルに接続された線のビジュアライゼーション &#x200B;](assets/table-line-viz.png)

### 折れ線グラフのビジュアライゼーションに含めるデータを選択

接続された線のビジュアライゼーションに含まれるデータは、フリーフォームテーブルで選択されているセルに応じて異なります。

フリーフォームテーブルのすべてのデータのトレンドを表示するには、フリーフォームテーブルのスパークラインセルを選択します。

スパークライン セルを選択すると、セルが濃い灰色で表示されます。

![&#x200B; スパークラインを選択 &#x200B;](assets/table-sparkline-selected.png)

接続されたテーブルのスパークライン セルを選択した場合、線のビジュアライゼーションには次のものが含まれます。

* 列内のすべてのデータのトレンドデータ

* テーブルディメンションに適用される検索フィルター条件

  詳しくは、「[&#x200B; フィルターと並べ替え &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)」を参照してください。

接続されたテーブルのスパークラインが選択されていない場合、折れ線グラフのビジュアライゼーションには次のものが含まれます。

* 接続されたテーブルで選択された行のデータ。 行が選択されていない場合、接続されたテーブルの最初のディメンションのデータのみが表示されます。

* テーブルディメンションに適用された検索フィルター条件は無視されます

  詳しくは、「[&#x200B; フィルターと並べ替え &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)」を参照してください。


## 接続線のビジュアライゼーションにフィルター条件を含める

フィルター条件が連結線のビジュアライゼーションに含まれるタイミングについて詳しくは、[&#x200B; スパークラインと線のビジュアライゼーションのトレンドデータにフィルター条件を含める &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#include-filter-criteria-in-trended-data-in-sparklines-and-line-visualizations) を参照してください。

