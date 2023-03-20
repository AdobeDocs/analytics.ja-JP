---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ要素の表示
feature: Components
role: User, Admin
source-git-commit: 8edd7b1b90e2ac3137bea734e5a0f1cb8004e743
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 59%

---

# データ要素でのコンポーネント情報の表示

{{release-limited-testing}}

データ要素を使用すると、コンポーネントの説明、類似のコンポーネント、コンポーネントが頻繁に使用される他のコンポーネントなど、コンポーネントに関する情報を表示できます。

データ要素でコンポーネントに関する情報を表示するには：

1. 表示するコンポーネントを含む Analysis Workspace プロジェクトに移動します。

1. Analysis Workspace の左側のパネルにある「[!UICONTROL **データ要素**]」アイコンを選択します（データ要素にアクセスする別の方法については、[データ要素の概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)の「データ要素へのアクセス」を参照してください）。

   データ要素ウィンドウが表示されます。

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 表示するコンポーネントを含むレポートスイートがドロップダウンメニューで選択されます。デフォルトでは、既に存在するレポートスイートが表示されます。

1. （オプション）検索フィールドに、表示するコンポーネントの名前の入力します。

   コンポーネント名の横にアイコンが表示され、コンポーネントのタイプが示されます。

   | アイコン | 意味 |
   |---------|----------|
   | ![Dimensionアイコン](assets/dimension-icon.png) | を示します。 **ディメンション**. DimensionはAdobeが提供します。 既存のディメンションは変更できず、新しいディメンションは作成できません。 |
   | ![指標アイコン](assets/default-metric-icon.png) | を示します。 **標準指標** （未計算）。 標準指標はAdobeで提供され、変更できません。 |
   | ![Adobeアイコン](assets/default-calc-metric-icon.png) | を示します。 **計算指標テンプレート**. これらは、Adobeが提供し、変更できない計算指標です。 |
   | ![計算ツールアイコン](assets/calculated-metric-icon-created.png) | を示します。 **計算指標** 組織の Analytics 管理者が作成した <!-- Delete all the comments... Components with this icon can be modified by an Analytics administrator. New calculated metrics can be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![セグメントアイコン](assets/segment-icon.png) | を示します。 **セグメント**. セグメントは、Adobeが提供するセグメントでも、組織の Analytics 管理者が作成するセグメントでもかまいません。<!-- Segments that were created byComponents with this icon can be modified by an Analytics administrator, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md). New calculated metrics can also be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![日付範囲アイコン](assets/date-range-icon.png) | を示します。 **日付範囲**. 日付範囲は、Adobeが指定した日付範囲でも、組織の Analytics 管理者が作成した日付範囲でもかまいません。 <!-- Components with this icon can be modified by an Analytics administrator. New date ranges can also be created by an Analytics administrator, as described in [Create custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). --> |

{{dd-filter-criteria}}

1. コンポーネントのリストから、表示するコンポーネントを選択します。

   コンポーネントに関する次の情報が表示されます。

   {{dd-component-information}}

1. （オプション）データディクショナリからAnalysis Workspaceにコンポーネントをドラッグします。