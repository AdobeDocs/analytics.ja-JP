---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ要素でのエントリの編集
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: a6805f0944570bee265d5db9a159ae24e0694837
workflow-type: ht
source-wordcount: '375'
ht-degree: 100%

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

   コンポーネントのタイプは、カラーとアイコンの両方で識別できます。**ディメンション** ![ディメンションアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) はオレンジ色、**セグメント** ![セグメントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) は青色、**日付範囲** ![日付範囲アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) は紫色、**指標** ![指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) は緑色です。Adobe アイコンは計算指標テンプレートまたはセグメントテンプレートのいずれか、電卓アイコン ![電卓アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) は組織の Analytics 管理者によって作成された計算指標を示します。

{{dd-filter-criteria}}

1. （オプション）「**並べ替え**」アイコン ![コンポーネントを並べ替えアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) を選択し、次のフィルターオプションのいずれかを選択してコンポーネントのリストを並べ替えます。

   {{components-sort-options}}

1. コンポーネントのリストから、編集するコンポーネントを選択します。

1. コンポーネント名の横にある&#x200B;**編集**&#x200B;アイコン ![データ要素編集アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) を選択します。

1. コンポーネントに関する次の情報を編集します。

   {{dd-component-information}}

1. **保存**&#x200B;アイコン ![データ要素保存アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) をクリックして、変更内容を保存します。
