---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: データ要素の表示
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
source-git-commit: a6805f0944570bee265d5db9a159ae24e0694837
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 57%

---

# データ要素でのコンポーネント情報の表示

データ要素を使用すると、コンポーネントの説明、類似のコンポーネント、コンポーネントが頻繁に使用される他のコンポーネントなど、コンポーネントに関する情報を表示できます。

データ要素でコンポーネントに関する情報を表示するには：

1. 表示するコンポーネントを含む Analysis Workspace プロジェクトに移動します。

1. Analysis Workspace の左側のパネルにある「[!UICONTROL **データ要素**]」アイコンを選択します（データ要素にアクセスする別の方法については、[データ要素の概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)の「データ要素へのアクセス」を参照してください）。

   データ要素ウィンドウが表示されます。

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 表示するコンポーネントを含むレポートスイートがドロップダウンメニューで選択されます。デフォルトでは、既に存在するレポートスイートが表示されます。

1. （オプション）検索フィールドに、表示するコンポーネントの名前の入力します。

   コンポーネントの種類は、色とアイコンの両方で識別できます。 **Dimension** ![Dimensionアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) オレンジ色です **セグメント** ![セグメントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 青い **日付範囲** ![日付範囲アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 紫色で **指標** ![指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) は緑です。 Adobeアイコンは、計算指標テンプレートまたはセグメントテンプレート、および計算ツールアイコンを示します ![計算ツールアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) は、組織の Analytics 管理者が作成した計算指標を示していました。

{{dd-filter-criteria}}

1. （オプション） **並べ替え** アイコン ![コンポーネントを並べ替えアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)次に、次のいずれかのフィルターオプションを選択して、コンポーネントのリストを並べ替えます。

   {{components-sort-options}}

1. コンポーネントのリストから、表示するコンポーネントを選択します。

   コンポーネントに関する次の情報が表示されます。

   {{dd-component-information}}

1. （オプション）データディクショナリからAnalysis Workspaceにコンポーネントをドラッグします。
