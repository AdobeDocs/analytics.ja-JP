---
title: 分類ジョブマネージャー
description: 分類セットから生成された、現在の分類ジョブと完了した分類ジョブを表示する方法について説明します。
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: 2ced7cd61c4119347be2ef0fba9b8d60ee6c4df2
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 2%

---

# 分類ジョブの表示とアクション

分類ジョブマネージャーには、分類セット用に生成された、現在の分類ジョブと完了した分類ジョブが表示されます。 マネージャーを使用して、特定のジョブの分類データまたはテンプレートをダウンロードすることもできます。

分類ジョブを表示して処理する手順は、次のとおりです。


1. Adobe Analyticsの上部メニューバーで **[!UICONTROL コンポーネント]** を選択し、**[!UICONTROL 分類セット]** を選択します。
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


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

You cannot create jobs from this interface. Create jobs by uploading data to a classification set (either manually or through a configured external location), requesting a download file, or requesting a template file.

## Filter classification sets

The left side of the Classification set job manager provides filter settings to locate the desired job. Clicking the filter icon toggles the filter settings visibility. You can filter Classification sets by **[!UICONTROL Classification set]**, **[!UICONTROL Completion time]**, **[!UICONTROL Status]**, **[!UICONTROL Job Type]**, or **[!UICONTROL Source]**.

![Classification set job filters](../assets/classification-set-job-filters.png)

Additional filter options are available above the Classification set job manager columns:

* **[!UICONTROL Search by title]**: Search for jobs by filename.
* **[!UICONTROL Load more]**: The Classification set job manager initially displays up to 1000 jobs. If more jobs exist, click this button to load 1000 more jobs.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Filename] and [!UICONTROL Completion time].

## Classification set job manager columns

The following columns are available in the Classification set job manager:

* **[!UICONTROL Filename]**: The name of the upload or download file.
* **[!UICONTROL Classification set]**: The name of the Classification set that the file applies to. You can click the Classification set name to reach the Classification set's [Settings](manage/settings.md).
* **[!UICONTROL Size]**: The size of the file.
* **[!UICONTROL Status]**: The status of the job processing the file.
  * **[!UICONTROL Created]**: The job was submitted.
  * **[!UICONTROL Queued]**: The file is ready to be processed, and is waiting for a classification server to process the file.
  * **[!UICONTROL Validated]**: The file is valid and is waiting to be processed.
  * **[!UICONTROL Failed validation]**: The file is formatted incorrectly or otherwise invalid. The file does not go through processing.
  * **[!UICONTROL Processing]**: The file is actively being processed by Adobe.
  * **[!UICONTROL Failed processing]**: The file failed processing.
  * **[!UICONTROL Complete]**: Processing is complete. Classification data is visible in reporting.
  * **[!UICONTROL Failed]**: Generic failure not related to validation or processing.
* **[!UICONTROL Job type]**: The type of job.
* **[!UICONTROL Source]**: The job source.
* **[!UICONTROL File download]**: Only applies to download jobs, such as downloading classification data or downloading templates. When a download is ready, this column provides a download link.
* **[!UICONTROL Modified lines]**: The number of modified lines.
* **[!UICONTROL Completed lines]**: The number of completed lines.
* **[!UICONTROL Completion time]**: The date and time that the job completed (or failed).
-->