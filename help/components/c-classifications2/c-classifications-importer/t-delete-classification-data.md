---
description: 分類データを削除する方法を説明する手順。
solution: Analytics
subtopic: Classifications
title: 分類データの削除
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 分類データの削除

分類データを削除する方法について手順を説明します。

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. 分類データを削除するレポートスイートおよびデータセットを選択します。
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. このコマンドは、特定のキーについては分類があたかも発生しなかったかのように扱います。このコマンドでは分類と列データが参照テーブルから完全に削除されます。

   **注意**:deletekeyを含む列は1つだけ必要 [!DNL ~です~]。 The [!DNL ~empty~] command works at the cell level (key and column combination), so you need [!DNL ~empty~] in the classification column you want to remove. However, [!DNL ~deletekey~] works at the row level (the key and all associated metadata), so it only needs to appear in one of the columns in the row. このコマンドは、行からメタデータをすべて削除します。アドビでは、キーが分類されたことが一度もなかったかのようにこのコマンドを解釈し、「[なし](/help/components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF)」カテゴリに表示します。

1. ファイルを保存し、「[!UICONTROL ファイルのインポート]」タブを使用してアップロードします。

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **このコマンドのプロパティ**

* [!DNL ~空白は~] 、スペースを含まない小文字にする必要があります。 以下の入力は無効です。

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~Empty~]

* キー列の値を削除することはできません。このデータは、レポーティングに直接渡される永久的なものです。
* 下位分類が設定された分類値を削除すると、下位分類も削除されます。下位分類ではその親がキー値となっており、キー値がない状態では分類が存在することはできないからです。
* 親分類はそのままに、下位分類のデータを削除することは可能です。

