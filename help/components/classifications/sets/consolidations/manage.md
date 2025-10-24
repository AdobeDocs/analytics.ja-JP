---
title: 分類セット統合の管理
description: 1 つ以上の分類セットを 1 つの分類セットに統合する方法を説明します。
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: 77599d015ba227be25b7ebff82ecd609fa45a756
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 3%

---

# 分類の統合の管理

類似の分類データを含む分類セットが複数ある場合は、それらを 1 つの分類セットに統合できます。 2 つ以上の分類セットを統合すると、Adobeによって、個々の分類セットからのすべての分類データを含む新しい分類セットが生成されます。 統合は、多くのレポートスイートにデータをアップロードした場合に役立ちます。 または、同じ分類データを含むディメンションがあり、それらを 1 つのワークフローに結合したい場合です。

分類セット統合マネージャーを表示するには、Adobe Analyticsの製品管理者アクセス権が必要です。



分類連結を管理する手順は、次のとおりです。

1. メインインターフェイスで **[!UICONTROL コンポーネント]** を選択し、**[!UICONTROL 分類セット]** を選択します。
1. **[!UICONTROL 分類セット]** で、「**[!UICONTROL 連結]**」タブを選択します。


## 分類統合マネージャー

**[!UICONTROL 分類セット – 連結]** マネージャーには、次のインターフェイス要素があります。

![ 分類セット – 連結マネージャー ](assets/classifications-sets-consolidations.png)



### 分類の統合リスト

リスト ➊ には、作成および検証され、統合対象となる可能性のある分類の統合が表示されます。 リストには、次の列があります。

| 列 | 説明 |
|---|---|
| **[!UICONTROL 連結名]** | 分類セット統合の名前。 |
| **[!UICONTROL 現在のジョブ]** | 分類セットの統合に関連付けられたジョブ。 |
| **[!UICONTROL ステータス]** | 分類セットの統合のステータス。 **[!UICONTROL Created]**、**[!UICONTROL Cancelled]**、**[!UICONTROL Canceling]**、**[!UICONTROL Validating]**、**[!UICONTROL Failed Validation]**、**[!UICONTROL Validated]**、**[!UICONTROL Comparising]**、**[!UICONTROL Comparison Failed]**、**[!UICONTROL Consolidation]**、**[!UICONTROL Submitted]**、ConsolidationConsolidationFailed、**[!UICONTROL ConsolidationFailed]** **** **** **** **** **** **** |
| **[!UICONTROL 作成時間]** | 分類セットの統合の作成時間。 |
| **[!UICONTROL 完了時間]** | 分類の統合の完了時間。 |


分類統合リストの列のサイズを変更するには、次の操作を行います。

* 列区切り記号の上にマウスポインターを置き、列区切り記号を目的の列幅までドラッグします。
* 「![ 山形の下 ](/help/assets/icons/ChevronDown.svg)」を選択し、「**[!UICONTROL 列のサイズ変更]**」を選択します。 サイズ変更ボタンが付いた縦線を使用すると、列のサイズを目的のサイズに変更できます。

分類統合リストで列を並べ替えるには

* ![ChevronDown](/help/assets/icons/ChevronDown.svg) を選択し、**[!UICONTROL 昇順で並べ替え]** または **[!UICONTROL 降順で並べ替え]** を選択します。 矢印（↑↓）は、列の並べ替え方法と列を示します。

### 検索とボタン

分類の統合リストの上部に ➋ る領域で、次の操作を実行できます。

* 分類統合を検索 ![ 検索 ](/help/assets/icons/Search.svg) します。 結果は、分類の統合リストに表示されます。 ![CrossSize200](/help/assets/icons/CrossSize200.svg) を選択して、検索をクリアします。
* 分類セット統合リストに適用されるフィルターを削除します。 ![CrossSize100](/help/assets/icons/CrossSize100.svg) を選択して、フィルターを削除します。
* 新しい分類セット統合を作成します。 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]** を選択して、分類セット統合ダイアログを開き、新しい分類セット統合を定義します。
* 分類統合リストの列を定義します。 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を選択し、**[!UICONTROL テーブルをカスタマイズ]** ダイアログの **[!UICONTROL 表示する列を選択]** の下に表示する列を選択します。 「**[!UICONTROL 適用]**」を選択して、列設定を適用します。


### アクションバー

分類セットリストで 1 つ以上の分類セットを選択すると、青いアクションバー ➌ 表示されます。 アクションバーでは、次のアクションを使用できます。

| アイコン | アクション | 説明 |
|---|---|---|
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 編集]** | [ 分類セットの統合の編集 ](process.md#edit-a-consolidation) |
| ![ViewDetail](/help/assets/icons/ViewDetail.svg) | **[!UICONTROL 表示]** | 分類セット統合の詳細を表示します。 ステータスに応じて、連結を [ 承認 ](process.md#approve) または [ キャンセル ](process.md#cancel) できます。 |


### フィルターパネル

![ フィルター ](/help/assets/icons/Filter.svg) を選択すると、分類統合リストをフィルタリングできるフィルターパネル ➍ が表示されます。 次の項目でフィルタリングできます。

* **[!UICONTROL ステータス]**。 ステータスの分類統合リストをフィルタリングするために、可能な値の 1 つを選択します。 |
* **[!UICONTROL 完了時間]**. 可能な値の 1 つを選択して、完了時に分類の統合リストをフィルタリングします。
* **[!UICONTROL 作成時刻]**. 可能な値の 1 つを選択して、完了時に分類の統合リストをフィルタリングします。


「![ フィルター ](/help/assets/icons/Filter.svg) **[!UICONTROL フィルターを非表示]**」を選択して、フィルターパネルを非表示にします。

フィルターパネルに表示されるフィルターは、プリロードされた分類の統合のオプションを反映することに注意してください。


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]**

Once a consolidation is run, the original classification sets are removed, with the consolidated classification set taking their place. Click **[!UICONTROL Add]** to [Create a consolidation](process.md).

## Filter classification sets

The left side of the Classification set consolidation manager provides filter settings to locate the desired consolidation. Clicking the filter icon toggles the filter settings visibility. You can filter consolidations by **[!UICONTROL Status]**, **[!UICONTROL Completion time]**, or **[!UICONTROL Creation time]**.

![Classification set consolidation filters](../../assets/classification-set-consolidation-filters.png)

Additional filter options are available above the Classification set consolidation manager columns:

* **[!UICONTROL Search by title]**: Search for consolidations by name.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Name].

## Classification set consolidation manager columns

The following columns are available in the Classification set consolidation manager:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Current job]**: The current job. 
* **[!UICONTROL Status]**: The status of the consolidation. 
* **[!UICONTROL Creation date]**: The date and time that the consolidation was created.
* **[!UICONTROL Completion date]**: The date and time that the consolidation completed (or failed).

-->
