---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ要素でのエントリの編集
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: 631f84794203cb0a1154d68149c9d64d7247ecd3
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 70%

---

# データ要素でのコンポーネントエントリの編集

Analytics 管理者は、特定のレポートスイートのデータ要素でのコンポーネントエントリを編集できます。 変更内容は、レポートスイートのすべてのユーザーに表示されます。

データ要素でのコンポーネントを編集するには：

1. 編集するコンポーネントを含む Analysis Workspace プロジェクトに移動します。

1. Analysis Workspace の左側のパネルにある「**データ要素**」アイコンを選択します（データ要素にアクセスする別の方法については、[データ要素の概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)の「データ要素へのアクセス」を参照してください）。

   データ要素ウィンドウが表示されます。

   ![データ要素の管理者表示](assets/data-dictionary-admin.png)

1. ドロップダウンメニューで正しいレポートスイートが選択されます。デフォルトでは、既に存在するレポートスイートが表示されます。

1. （オプション）検索フィールドに、編集するコンポーネントの名前を入力します。

   コンポーネントの種類は、色とアイコンの両方で識別できます。 **Dimension** ![Dimensionアイコン](assets/dimension-icon.png) オレンジ色です **セグメント** ![セグメントアイコン](assets/segment-icon.png) 青い **日付範囲** ![日付範囲アイコン](assets/date-range-icon.png) 紫色で **指標** ![指標アイコン](assets/default-metric-icon.png) は緑です。 Adobeアイコン ![Adobeアイコン](assets/default-calc-metric-icon.png) は、計算指標テンプレートまたはセグメントテンプレート、および計算ツールアイコンを示します ![計算ツールアイコン](assets/calculated-metric-icon-created.png) は、組織の Analytics 管理者が作成した計算指標を示していました。

{{dd-filter-criteria}}

1. （オプション） **並べ替え** アイコン ![コンポーネントを並べ替えアイコン](assets/component-sort-icon.png)次に、次のいずれかのフィルターオプションを選択して、コンポーネントのリストを並べ替えます。

   {{components-sort-options}}

1. コンポーネントのリストから、編集するコンポーネントを選択します。

1. コンポーネント名の横にある&#x200B;**編集**&#x200B;アイコン ![データ要素編集アイコン](assets/data-dictionary-edit-icon.png) を選択します。

1. コンポーネントに関する次の情報を編集します。

   {{dd-component-information}}

1. **保存**&#x200B;アイコン ![データ要素保存アイコン](assets/data-dictionary-save-icon.png) をクリックして、変更内容を保存します。
