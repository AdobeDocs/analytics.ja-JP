---
description: 分類データを削除する方法について手順を説明します。
seo-description: 分類データを削除する方法を説明する手順。
seo-title: 分類データの削除
solution: Analytics
subtopic: '分類      '
title: 分類データの削除
topic: 管理ツール
uuid: 5b1b0ac7- ee52-4fd8- b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 分類データの削除

分類データを削除する方法について手順を説明します。

1. **[!UICONTROL 管理者]** / **[!UICONTROL 分類インポーター]**&#x200B;をクリックします。
1. **[!UICONTROL 「ブラウザーエクスポート]**」をクリックします。
1. 分類データを削除するレポートスイートおよびデータセットを選択します。
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. このコマンドは、特定のキーについては分類があたかも発生しなかったかのように扱います。このコマンドでは分類と列データが参照テーブルから完全に削除されます。

   **注意**:deletekeyを含む [!DNL ~列のみが必要~]です。[!DNL ~空~] のコマンドはセルレベル（キーと列の組み合わせ）で動作するので、削除する分類列で [!DNL ~空~] にする必要があります。[!DNL ~ただし、deletekey~] は行レベル（キーとすべての関連メタデータ）で動作するので、行の列の1つにのみ表示される必要があります。このコマンドは、行からメタデータをすべて削除します。アドビでは、キーが分類されたことが一度もなかったかのようにこのコマンドを解釈し、「[なし](../../../components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF)」カテゴリに表示します。

1. ファイルを保存し、「[!UICONTROL ファイルのインポート]」タブを使用してアップロードします。

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **このコマンドのプロパティ**

* [!DNL ~empty~] はスペースなしで小文字にする必要があります。以下の入力は無効です。

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~Empty~]

* キー列の値を削除することはできません。このデータは、レポーティングに直接渡される永久的なものです。
* 下位分類が設定された分類値を削除すると、下位分類も削除されます。下位分類ではその親がキー値となっており、キー値がない状態では分類が存在することはできないからです。
* 親分類はそのままに、下位分類のデータを削除することは可能です。

