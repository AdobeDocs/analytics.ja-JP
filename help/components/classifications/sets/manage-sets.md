---
title: 分類セットの管理
description: Adobe Analyticsで分類セットを管理します。
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: eb12185be8d6e2e6dc15df9da17ce34b5f6b9c80
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 8%

---

# 分類セットの管理

分類セット管理インターフェイスで、分類セットの作成、名前変更、編集、統合、削除、タグ付けを行うことができます。 また、でフィルタリングし、特定の分類セットを検索することもできます。

分類セットを管理するには：

1. Adobe Analytics の上部メニューバーで&#x200B;**[!UICONTROL コンポーネント]**&#x200B;を選択し、**[!UICONTROL 分類セット]**&#x200B;を選択します。
1. **[!UICONTROL 分類セット]**&#x200B;で、「**[!UICONTROL 分類セット]**」タブを選択します。

## 分類セットマネージャー

**[!UICONTROL 分類セット]** マネージャーには、次のインターフェイス要素があります。

![ 分類セットマネージャー ](assets/classification-sets-manage.png)


### 分類セット リスト

**[!UICONTROL 分類セット]** リストには、すべての分類セット ➊ 表示されます。 リストには、次の列があります。

| 列 | 説明 |
|---|---|
| **[!UICONTROL 分類セット]** | 分類セットの名前。 [ 分類セットを編集 ](create-set.md#edit-a-classification-set) する名前を選択します。 |
| **[!UICONTROL サブスクリプション]** | 分類セットが適用される購読の数。 |
| **[!UICONTROL 分類]** | 分類セットに含まれる分類ディメンションの数。 |
| **[!UICONTROL 自動]** | 分類セットは、クラウドの場所からデータを自動的にインポートするように設定されているかどうか。 この自動処理は、[ 分類セットスキーマ ](manage/schema.md) の一部として設定できます。 |
| **[!UICONTROL 最終変更日]** | 分類セットの最終変更のタイムスタンプ。 |

分類セットリストの列のサイズを変更するには、次の操作を行います。

* 列区切り記号の上にマウスポインターを置き、列区切り記号を目的の列幅までドラッグします。
* 「![ 山形の下 ](/help/assets/icons/ChevronDown.svg)」を選択し、「**[!UICONTROL 列のサイズ変更]**」を選択します。 サイズ変更ボタンが付いた縦線を使用すると、列のサイズを目的のサイズに変更できます。

分類セットリストの列を並べ替えるには

* ![ChevronDown](/help/assets/icons/ChevronDown.svg) を選択し、**[!UICONTROL 昇順で並べ替え]** または **[!UICONTROL 降順で並べ替え]** を選択します。 矢印（↑↓）は、列の並べ替え方法と列を示します。

### 検索とボタン

分類セット リストの上部にある ➋ 領域で、次の操作を実行できます。

* 分類セットを検索 ![ 検索 ](/help/assets/icons/Search.svg) します。 結果は、分類セットのリストに表示されます。 ![CrossSize200](/help/assets/icons/CrossSize200.svg) を選択して、検索をクリアします。
* 分類セットのリストに適用されているフィルターを削除します。 ![CrossSize100](/help/assets/icons/CrossSize100.svg) を選択して、フィルターを削除します。
* ![MoreCircle](/help/assets/icons/MoreCircle.svg) を選択すると、追加の分類セットが 1,000 個読み込まれます。 最初に、分類セットリストには、最大 1,000 個の分類セットが表示されます。
* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]** を選択して [ 新しい分類セットを作成 ](create-set.md#create-a-classification-set) します。
* 分類セットリストの列を定義します。 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を選択し、**[!UICONTROL テーブルをカスタマイズ]** ダイアログの **[!UICONTROL 表示する列を選択]** の下に表示する列を選択します。 「**[!UICONTROL 適用]**」を選択して、列設定を適用します。


### アクションバー

分類セットリストで 1 つ以上の分類セットを選択すると、青いアクションバー ➌ 表示されます。 アクションバーでは、次のアクションを使用できます。

| アイコン | アクション | 説明 |
|---|---|---|
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 編集]** | 分類セットビルダーで [ 分類セットを編集 ](create-set.md#edit-a-classification-set) します。 |
| ![名前変更](/help/assets/icons/Rename.svg) | **[!UICONTROL 名前変更]** | 分類セットの名前を変更します。<br/>**[!UICONTROL 名前を変更：_分類セット_]**ダイアログで新しい名前を入力し、**[!UICONTROL 名前を変更]**を選択します。 |
| ![Merge](/help/assets/icons/Merge.svg) | **[!UICONTROL 統合]** | [ 分類セットを統合 ](/help/components/classifications/sets/consolidations/manage.md)。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 分類セットを削除します。<br/>**[!UICONTROL 分類セット _を削除_ ますか？ダ]** アログが表示されます。 分類セットの削除は元に戻すことができません。 この分類セットを使用するスケジュール済プロジェクトまたは連結は、スケジュール済プロジェクトを再保存するか、スケジュール済み連結を再検証するまで、この分類セットの定義を引き続き使用します。 分類セットを削除するには、「**[!UICONTROL 削除]**」を選択します。 |
| ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL タグ]** | 分類セットにタグを付けます。<br/>**[!UICONTROL タグ：_分類セット_]**ダイアログで、「**[!UICONTROL タグ]**」ドロップダウンメニューから 1 つ以上のタグを選択してタグを追加します。 または、1 つ以上の新しいタグを入力します。 タグを削除するには、![CrossSize100](/help/assets/icons/CrossSize100.svg) を使用します。 <br/> 「**[!UICONTROL 保存]**」を選択して、タグを保存します。 |


### フィルターパネル

「![ フィルター ](/help/assets/icons/Filter.svg)」を選択すると、分類セットリストをフィルタリングできるフィルターパネル ➍ が表示されます。 次の項目でフィルタリングできます。

* **[!UICONTROL タグ]** 1 つ以上のタグを選択して、タグの分類セットリストをフィルタリングします。
* **[!UICONTROL レポートスイート]**。 1 つ以上のレポートスイートを選択して、レポートスイートの分類セットリストをフィルタリングします。

「![ フィルター ](/help/assets/icons/Filter.svg) **[!UICONTROL フィルターを非表示]**」を選択して、フィルターパネルを非表示にします。

フィルターパネルに表示されるフィルターは、プリロードされた分類セットのオプションを反映することに注意してください。
