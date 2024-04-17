---
title: 分類セットスキーマ
description: 個々の分類セットのスキーマを表示および編集します。
exl-id: 4a7c5bfe-ff2b-4380-af46-435801d73c1e
feature: Classifications
source-git-commit: 95767d10f63e20d5943fa95be3f2fe8f88e67e97
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 43%

---

# スキーマ

この分類セットに対して現在設定されている分類ディメンションを表示します。

**[!UICONTROL Components]** > **[!UICONTROL 分類セット]** > **[!UICONTROL セット]** > 目的の分類セット名をクリックします > **[!UICONTROL スキーマ]**

次のボタンを使用できます。

<!--* **[!UICONTROL Add]**: Adds an empty row so that you can add a classification dimension to the schema.-->
* **[!UICONTROL アップロード]**：1 つ以上の分類ディメンションの分類データを手動でアップロードします。`JSON`, `CSV`, `TSV`、および `TAB` ファイルがサポートされています。 有効なファイルをアップロードすると、分類するデータのテーブルプレビューが表示されます。
   * **[!UICONTROL ファイルのエンコーディング]**：このドロップダウンを使用して、正しいファイルエンコーディングを選択します。 有効なオプションは、[!UICONTROL UTF-8] および [!UICONTROL Latin1] です。
   * **[!UICONTROL リスト区切り]**：正しいリスト区切り文字を選択します。 ダウンロードしたファイルまたはテンプレートファイルを使用する場合は、ここの[!UICONTROL リスト区切り文字]がファイルのダウンロード時の[!UICONTROL リスト区切り文字]と一致していることを確認してください。
   * **[!UICONTROL 適用]**：アップロードした分類データを分類セットに保存します。

  ![分類セットのアップロード](../../assets/classification-set-upload.png)

* **[!UICONTROL ダウンロード]**：キー値とその分類列をダウンロードします。
   * **[!UICONTROL 行]**：ダウンロードファイルに含める行の最大数。
   * **[!UICONTROL 次の期間に受信した行をダウンロード]**：レポートに表示されるときにキー値をフィルタリングできるカレンダー日付選択。この日付範囲でキー値が収集されなかった場合、ダウンロードされたファイルには表示されません。
   * **[!UICONTROL 返されたデータ]**：関連する分類データに基づいて、ダウンロードしたファイルに含まれるキー値をフィルタリングできるドロップダウンリスト。
      * **[!UICONTROL すべての分類済み値]**：分類データが 1 つ以上の列に含まれる行を含みます。
      * **[!UICONTROL すべての未分類の値]**：分類データが 1 つ以上の列に存在しない行を含みます。
   * **[!UICONTROL ファイル形式]**：ダウンロードファイルのファイル形式を決定するドロップダウンリスト。 オプションには、[!UICONTROL JSON]、[!UICONTROL コンマ区切り値]および [!UICONTROL Excel タブ区切り値]があります。
   * **[!UICONTROL ファイルのエンコーディング]**：ファイルのエンコーディングを決定するドロップダウンリスト。 オプションには、[!UICONTROL UTF-8] および [!UICONTROL Latin1] があります。UTF-8 をお勧めします。

  ![分類セットのダウンロード](../../assets/classification-set-download.png)

* **[!UICONTROL テンプレート]**：テンプレートファイルをダウンロードします。このファイルは、分類データやキー値が含まれていないことを除けば、[!UICONTROL ダウンロード]ボタンに似ています。
   * **[!UICONTROL ファイル形式]**：テンプレートファイルのファイル形式を決定するドロップダウンリスト。 オプションには、[!UICONTROL コンマ区切り値]および [!UICONTROL Excel タブ区切り値]があります。
   * **[!UICONTROL ファイルのエンコーディング]**：ファイルのエンコーディングを決定するドロップダウンリスト。 オプションには、[!UICONTROL UTF-8] および [!UICONTROL Latin1] があります。UTF-8 をお勧めします。
   * **[!UICONTROL リスト区切り文字]**：各行の分類列を区切るリスト区切り文字を決定するドロップダウンリスト。

  ![分類セットテンプレート](../../assets/classification-set-template.png)

* **[!UICONTROL ジョブ履歴]**：に移動するためのショートカットリンク [ジョブマネージャー](../job-manager.md)。この分類セットのジョブのみを表示します。
* **[!UICONTROL 自動化]**：外部ストレージの場所からデータを自動的に取り込みます。
   * **[!UICONTROL 場所アカウント]**：組織が設定した既存の場所アカウントを示すドロップダウンリスト。 組織でまだ場所アカウントを設定していない場合は、次のオプションを選択して設定できます。 [!UICONTROL **新しいアカウントを作成**].

     場所アカウントの設定については [クラウドのインポートおよびエクスポートアカウントの設定](/help/components/locations/configure-import-accounts.md).

   * **[!UICONTROL 場所]**：組織が設定した既存の場所を示すドロップダウンリスト。 組織でまだ場所を設定していない場合は、次のオプションを選択して場所を設定できます [!UICONTROL **新しい場所を作成**].

     場所の設定については、を参照してください。 [クラウドの読み込み場所と書き出し場所の設定](/help/components/locations/configure-import-locations.md).

   * **[!UICONTROL 区切り文字]**：アップロードしたファイルの列区切り文字。 次のようなオプションがあります [!UICONTROL コンマ], [!UICONTROL セミコロン], [!UICONTROL コロン], [!UICONTROL 縦棒グラフ], [!UICONTROL スペース], [!UICONTROL スラッシュ], [!UICONTROL バックスラッシュ], [!UICONTROL Dash]、または [!UICONTROL アンダースコア].

   * **[!UICONTROL エンコード]**：ファイルのエンコーディングを決定するドロップダウンリスト。 オプションには、[!UICONTROL UTF-8] および [!UICONTROL Latin1] があります。UTF-8 をお勧めします。
