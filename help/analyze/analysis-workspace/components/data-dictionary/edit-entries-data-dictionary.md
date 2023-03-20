---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ要素でのエントリの編集
feature: Components
role: Admin
source-git-commit: 8edd7b1b90e2ac3137bea734e5a0f1cb8004e743
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 63%

---

# データ要素でのコンポーネントエントリの編集

{{release-limited-testing}}

Analytics 管理者は、特定のレポートスイートのデータ要素でのコンポーネントエントリを編集できます。 変更内容は、レポートスイートのすべてのユーザーに表示されます。

データ要素でのコンポーネントを編集するには：

1. 編集するコンポーネントを含む Analysis Workspace プロジェクトに移動します。

1. Analysis Workspace の左側のパネルにある「**データ要素**」アイコンを選択します（データ要素にアクセスする別の方法については、[データ要素の概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)の「データ要素へのアクセス」を参照してください）。

   データ要素ウィンドウが表示されます。

   ![データ要素の管理者表示](assets/data-dictionary-admin.png)

1. ドロップダウンメニューで正しいレポートスイートが選択されます。デフォルトでは、既に存在するレポートスイートが表示されます。

1. （オプション）検索フィールドに、編集するコンポーネントの名前を入力します。

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

1. コンポーネントのリストから、編集するコンポーネントを選択します。

1. コンポーネント名の横にある&#x200B;**編集**&#x200B;アイコン ![データ要素編集アイコン](assets/data-dictionary-edit-icon.png) を選択します。

1. コンポーネントに関する次の情報を編集します。

   {{dd-component-information}}

1. **保存**&#x200B;アイコン ![データ要素保存アイコン](assets/data-dictionary-save-icon.png) をクリックして、変更内容を保存します。
