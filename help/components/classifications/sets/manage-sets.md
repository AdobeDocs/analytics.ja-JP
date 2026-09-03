---
title: 分類セットの管理
description: Adobe Analyticsで分類セットを管理します。
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
TQID: https://experienceleague.adobe.com/qSpr-B-e-VdROnw3ngLDcoWqsLgiUDz7GRniffxOM2c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 621
ht-degree: 8%

---

# 分類セットの管理

分類セット管理インターフェイスでは、分類セットを作成、名前変更、編集、統合、削除、タグ付けすることができます。 また、特定の分類セットをフィルタリングして検索することもできます。

分類セットを管理するには：

1. Adobe Analytics の上部メニューバーで&#x200B;**[!UICONTROL コンポーネント]**&#x200B;を選択し、**[!UICONTROL 分類セット]**&#x200B;を選択します。
1. **[!UICONTROL 分類セット]**&#x200B;で、「**[!UICONTROL 分類セット]**」タブを選択します。

## 分類セットマネージャー

**[!UICONTROL 分類セット]** マネージャーには、次のインターフェイス要素があります。

![分類セット マネージャー](assets/classification-sets-manage.png)


### 分類セットリスト

**[!UICONTROL 分類セット]** リスト ➊には、すべての分類セットが表示されます。 リストには、次の列があります。

| 列 | 説明 |
|---|---|
| **[!UICONTROL 分類セット]** | 分類セットの名前。 名前を選択して[分類セットを編集](create-set.md#edit-a-classification-set)します。 |
| **[!UICONTROL サブスクリプション]** | 分類セットが適用されるサブスクリプションの数。 |
| **[!UICONTROL 分類]** | 分類セットに含まれる分類ディメンションの数。 |
| **[!UICONTROL 自動化]** | 分類セットは、クラウドの場所からデータを自動的に読み込むように設定されていますか？ この自動化は、[分類セットスキーマ &#x200B;](manage/schema.md)の一部として設定できます。 |
| **[!UICONTROL 最終変更日]** | 分類セットの最後の変更のタイムスタンプ。 |

分類セットリストの列のサイズを変更するには、次の操作を行います。

* 列区切り記号にカーソルを合わせ、列区切り記号を目的の列幅にドラッグします。
* ![ChevronDown](/help/assets/icons/ChevronDown.svg)を選択し、**[!UICONTROL 列のサイズ変更]**&#x200B;を選択します。 「サイズ変更」ボタンを使用して垂直線を使用すると、列のサイズを目的のサイズに変更できます。

分類セット リストの列を並べ替えるには

* ![ChevronDown](/help/assets/icons/ChevronDown.svg)を選択し、**[!UICONTROL 昇順を並べ替え]**&#x200B;または&#x200B;**[!UICONTROL 降順を並べ替え]**&#x200B;を選択します。 矢印（↑↓）は、どの列と列がどのように並べ替えられるかを示します。

### 検索とボタン

分類セット リストの上の領域➋で、次の操作を行うことができます。

* 分類セットを![検索](/help/assets/icons/Search.svg)します。 結果は、分類セットのリストに表示されます。 ![CrossSize200](/help/assets/icons/CrossSize200.svg)を選択して検索をクリアします。
* 分類セットリストに適用されているフィルターをすべて削除します。 フィルターを削除するには、![CrossSize100](/help/assets/icons/CrossSize100.svg)を選択します。
* 追加の1000個の分類セットを読み込むには、![MoreCircle](/help/assets/icons/MoreCircle.svg)を選択します。 最初、分類セットリストには最大1000個の分類セットが表示されます。
* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**&#x200B;を選択して[新しい分類セットを作成](create-set.md#create-a-classification-set)します。
* 分類セットリストの列を定義します。 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)を選択し、**[!UICONTROL テーブルをカスタマイズ]** ダイアログで、**[!UICONTROL の下に表示する列を選択して、]**&#x200B;を表示します。 **[!UICONTROL 適用]**&#x200B;を選択して、列設定を適用します。


### アクションバー

分類セットリストで1つ以上の分類セットを選択すると、青いアクションバー➌が表示されます。 アクションバーでは、次のアクションを使用できます。

| アイコン | アクション | 説明 |
|---|---|---|
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 編集]** | [分類セットビルダーで分類セット &#x200B;](create-set.md#edit-a-classification-set)を編集します。 |
| ![名前変更](/help/assets/icons/Rename.svg) | **[!UICONTROL 名前変更]** | 分類セットの名前を変更します。<br/> 「**[!UICONTROL 名前変更：_分類セット_]**」ダイアログで、新しい名前を入力し、**[!UICONTROL 名前変更]**」を選択します。 |
| ![Merge](/help/assets/icons/Merge.svg) | **[!UICONTROL 統合]** | [分類セットの統合](/help/components/classifications/sets/consolidations/manage.md)。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 分類セットを削除します。<br/>**[!UICONTROL 分類セット _を削除_?]** ダイアログが表示されます。 分類セットの削除を元に戻すことはできません。 この分類セットを使用するスケジュール済みプロジェクトまたは統合では、スケジュール済みプロジェクトを再保存するか、スケジュール済み統合を再検証するまで、この分類セットの定義が引き続き使用されます。 分類セットを削除するには、**[!UICONTROL 削除]**&#x200B;を選択します。 |
| ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL タグ]** | 分類セットにタグ付けします。<br/> 「**[!UICONTROL タグ：_分類セット_]**」ダイアログで、**[!UICONTROL タグ]**&#x200B;ドロップダウンメニューから1つ以上のタグを選択してタグを追加します。 または1つ以上の新しいタグを入力します。 タグを削除するには、![CrossSize100](/help/assets/icons/CrossSize100.svg)を使用します。 <br/> タグを保存するには、**[!UICONTROL 保存]**&#x200B;を選択します。 |


### フィルターパネル

分類セットリストをフィルタリングできるフィルターパネル ➍を表示するには、![&#x200B; フィルター](/help/assets/icons/Filter.svg)を選択します。 次の条件でフィルタリングできます。

* **[!UICONTROL タグ]** 1つ以上のタグを選択して、タグの分類セットリストをフィルタリングします。
* **[!UICONTROL レポートスイート]**。 1つ以上のレポートスイートを選択して、レポートスイートの分類セットリストをフィルタリングします。

「![&#x200B; フィルター](/help/assets/icons/Filter.svg) **[!UICONTROL フィルターを非表示]**」を選択して、フィルターパネルを非表示にします。

フィルターパネルに表示されるフィルターは、プリロードされた分類セットのオプションを反映しています。
