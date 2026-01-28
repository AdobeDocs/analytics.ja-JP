---
title: 分類ジョブマネージャー
description: 分類セットから生成された、現在の分類ジョブと完了した分類ジョブを表示する方法について説明します。
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: cfa8335008548254786e46dfe634229edad5bd54
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 4%

---

# 分類ジョブの表示とアクション

分類ジョブマネージャーには、分類セット用に生成された、現在の分類ジョブと完了した分類ジョブが表示されます。 マネージャーを使用して、特定のジョブの分類データまたはテンプレートをダウンロードすることもできます。

分類ジョブを表示して処理する手順は、次のとおりです。


1. Adobe Analytics の上部メニューバーで&#x200B;**[!UICONTROL コンポーネント]**&#x200B;を選択し、**[!UICONTROL 分類セット]**&#x200B;を選択します。
1. **[!UICONTROL 分類セット]** で、「**[!UICONTROL ジョブ]**」タブを選択します。

## 分類ジョブマネージャー

**[!UICONTROL 分類セット – ジョブ]** マネージャーには、次のインターフェイス要素があります。

![ 分類セット – ジョブマネージャー ](manage/assets/classifications-sets-jobs.png)



### 分類ジョブリスト

**[!UICONTROL 分類ジョブ]** リストには、分類ジョブ ➊ 表示されます。 リストには、次の列があります。

| 列 | 説明 |
|---|---|
| **[!UICONTROL ジョブ Id]** | 分類ジョブの識別子。 |
| **[!UICONTROL 分類セット]** | 分類ジョブに関連付けられた分類セット。 |
| **[!UICONTROL サイズ]** | 分類ジョブの一環としてエクスポートまたはインポートされたファイルのサイズ。 |
| **[!UICONTROL ステータス]** | 分類ジョブのステータス。 使用可能な値：**[!UICONTROL Created]**、**[!UICONTROL Queued]**、**[!UICONTROL Validated]**、**[!UICONTROL Failed validation]**、**[!UICONTROL Processing]**、**[!UICONTROL Done processing]**、**[!UICONTROL Failed processing]**、**[!UICONTROL Completed]**、または **[!UICONTROL Progress]** 表示された場合、アラート ![ アラート ](/help/assets/icons/Alert.svg) にポインタを合わせると、追加情報が表示されます。 |
| **[!UICONTROL ファイル名]** | 分類ジョブの一部としてファイルのインポートまたはエクスポートに使用する名前または機能を識別します。 使用可能な値： <ul><li>*値なし*</li><li>分類ジョブの一部として処理されるファイルの名前。</li><li>**[!UICONTROL SAINTのエクスポート]**: [ 従来の分類インターフェイス ](/help/components/classifications/importer/c-working-with-saint.md) からのエクスポートです。</li><li>**[!UICONTROL タイムスタンプ _での_ 分類セット _のエクスポート_]**：ジョブは、[ スキーマ ](manage/schema.md#download) インターフェイスからのダウンロードです。</li></ul> |
| **[!UICONTROL ジョブタイプ]** | 分類ジョブのタイプ。 使用可能な値：**[!UICONTROL Import]** または **[!UICONTROL Export]**。 |
| **[!UICONTROL ソース]** | 分類ジョブのソース。 **[!UICONTROL Web API]**、**[!UICONTROL ダイレクト API アップロード]**、**[!UICONTROL Adobe]**、**[!UICONTROL SAINT]**、**[!UICONTROL 不明]** のいずれかの値が使用されます。 |
| **[!UICONTROL 変更された行]** | 分類ジョブによって変更された変更済ラインの数です。 |
| **[!UICONTROL 合計行数]** | 分類ジョブが処理した合計行数。 |
| **[!UICONTROL 完了時間]** | 分類ジョブの完了時間。 |
| **[!UICONTROL ファイルのダウンロード]** | ![ ダウンロード ](/help/assets/icons/Download.svg) を使用して、分類ジョブに関連付けられたファイル（テンプレートまたはデータ）をダウンロードします。 |

分類ジョブリストの列のサイズを変更するには、次の操作を実行します。

* 列区切り記号の上にマウスポインターを置き、列区切り記号を目的の列幅までドラッグします。
* 「![ 山形の下 ](/help/assets/icons/ChevronDown.svg)」を選択し、「**[!UICONTROL 列のサイズ変更]**」を選択します。 サイズ変更ボタンが付いた縦線を使用すると、列のサイズを目的のサイズに変更できます。

分類ジョブリストの列を並べ替えるには

* ![ChevronDown](/help/assets/icons/ChevronDown.svg) を選択し、**[!UICONTROL 昇順で並べ替え]** または **[!UICONTROL 降順で並べ替え]** を選択します。 矢印（↑↓）は、列の並べ替え方法と列を示します。


### 検索とボタン

分類ジョブリストの上部にある領域 ➋ で、次の操作を実行できます。

* 分類ジョブを検索 ![ 検索 ](/help/assets/icons/Search.svg) します。 結果は、分類ジョブリストに表示されます。 ![CrossSize200](/help/assets/icons/CrossSize200.svg) を選択して、検索をクリアします。
* 分類ジョブリストに適用されているフィルターを削除します。 ![CrossSize100](/help/assets/icons/CrossSize100.svg) を選択して、フィルターを削除します。
* ![MoreCircle](/help/assets/icons/MoreCircle.svg) を選択して、追加の 1,000 個の分類ジョブを読み込みます。 最初に、分類セットリストには、最大 1,000 個の分類ジョブが表示されます。
* 分類セットジョブリストの列を定義します。 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を選択し、**[!UICONTROL テーブルをカスタマイズ]** ダイアログの **[!UICONTROL 表示する列を選択]** の下に表示する列を選択します。 「**[!UICONTROL 適用]**」を選択して、列設定を適用します。



### フィルターパネル

![ フィルター ](/help/assets/icons/Filter.svg) を選択すると、分類ジョブのリストをフィルタリングできるフィルターパネル ➌ が表示されます。 次の項目でフィルタリングできます。

* **[!UICONTROL 分類セット]**。 1 つ以上の分類セットを選択して、分類ジョブリストをフィルタリングします。
* **[!UICONTROL 完了時間]**. 可能な値の 1 つを選択して、完了時に分類ジョブリストをフィルタリングします。
* **[!UICONTROL ステータス]**。 可能な値の 1 つを選択して、ステータスの分類ジョブリストをフィルタリングします。
* **[!UICONTROL ジョブタイプ]**。 可能な値の 1 つを選択して、ジョブタイプの分類ジョブリストをフィルタリングします。
* **[!UICONTROL Source]**。 使用可能な値の 1 つを選択して、ソースの分類ジョブリストをフィルタリングします。


「![ フィルター ](/help/assets/icons/Filter.svg) **[!UICONTROL フィルターを非表示]**」を選択して、フィルターパネルを非表示にします。

フィルターパネルに表示されるフィルターは、プリロードされた分類ジョブのオプションを反映することに注意してください。
