---
title: 分類セットスキーマ
description: 個々の分類セットのスキーマを表示および編集する方法について説明します。
exl-id: 4a7c5bfe-ff2b-4380-af46-435801d73c1e
feature: Classifications
source-git-commit: e89d67d60313867a18b4d2a1e4e7a0e7da5dc31a
workflow-type: tm+mt
source-wordcount: '1579'
ht-degree: 5%

---

# 分類セットスキーマ

スキーマは、分類セットに対して定義した主要ディメンションに適用する分類のリストです。 例えば、製品をキーディメンションとして定義し、このフィールドに製品 SKU が含まれている場合、スキーマを使用して、製品名、製品カラー、製品サイズなどの分類を追加します。

分類セットのスキーマを編集するには：


1. Adobe Analytics の上部メニューバーで&#x200B;**[!UICONTROL コンポーネント]**&#x200B;を選択し、**[!UICONTROL 分類セット]**&#x200B;を選択します。
1. **[!UICONTROL 分類セット]**&#x200B;で、「**[!UICONTROL 分類セット]**」タブを選択します。
1. **[!UICONTROL 分類セット]** マネージャーで、スキーマを編集する分類セットを選択します。
1. **[!UICONTROL 分類セット：_分類セット名_]**ダイアログで、「**[!UICONTROL スキーマ]**」タブを選択します。 このタブは、次のインターフェイス要素で構成されます。

   ![ 分類セット – スキーマ ](assets/classification-sets-schema.png)

   * [分類リスト](#classification-list)
   * [検索](#search)
   * [アクション](#actions)
   * [アクションバー](#action-bar)

## 分類リスト

分類のリストには、次の列があります。

| 列 | 説明 |
|---|---|
| **[!UICONTROL 分類名]** | 分類に指定した名前。 |
| **[!UICONTROL ID 名]** | 分類に対するシステムの派生名。 この名前は読み取り専用で、ID 名を使用できます |
| **[!UICONTROL 分類者]** | 使用される場合、この分類の分類に使用されるルックアップ分類セットへのリンク。 |


## 検索

1 つ以上の分類をすばやく検索 ![ 検索 ](/help/assets/icons/Search.svg) できます。 検索をクリアするには、![CrossSize100](/help/assets/icons/CrossSize100.svg) を使用します。

## アクション

分類リストの上部にあるボタンとして、次のアクションを使用できます。

| アイコン | アクション | 説明 |
|---|---|---|
| ![追加](/help/assets/icons/Add.svg) | **[!UICONTROL 追加]** | リストに [ 分類を追加 ](#add) します。 |
| ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) | **[!UICONTROL アップロード]** | [JSON、CSV、TSV、TAB ファイルをアップロードします ](#upload)。 |
| ![ダウンロード](/help/assets/icons/Download.svg) | **[!UICONTROL ダウンロード]** | [ 分類データをダウンロード ](#download)。 |
| ![DocumentFragment](/help/assets/icons/DocumentFragment.svg) | **[!UICONTROL テンプレート]** | 分類データの [ テンプレートをダウンロード ](#template) します。 |
| ![ 履歴 ](/help/assets/icons/History.svg) | **[!UICONTROL ジョブ履歴]** | 選択した分類セットでフィルタリングした [ 分類セットジョブマネージャー ](/help/components/classifications/sets/job-manager.md) を表示します。 |
| ![ 歯車 ](/help/assets/icons/Gear.svg) | **[!UICONTROL 自動化]** | クラウドの場所を使用して [ 分類データの取り込みを自動化 ](#automate) します。 |


### 追加

新しい分類を追加するには、「![ 追加 ](/help/assets/icons/Add.svg)**[!UICONTROL 追加]**」を選択します。

![ 分類セット – スキーマに分類を追加 ](assets/classification-sets-schema-add-classification.png)

**[!UICONTROL 分類セット名 _の新しい分類を追加_]**ダイアログで、**[!UICONTROL 分類名]**を入力して&#x200B;**[!UICONTROL 追加]**を選択します。 分類がリストに追加されます。



### Upload

分類データを分類用のスキーマに読み込むには、![UploadToCloud](/help/assets/icons/UploadToCloud.svg)**[!UICONTROL Upload]** を選択します。


![ 分類セット – スキーマがファイルをアップロードします ](assets/classification-sets-schema-upload-file.png)

1. **[!UICONTROL 新しい分類を追加]** ダイアログで、次の操作を行います。

   * 分類データを含むファイルをドラッグし、**[!UICONTROL ここにドラッグ&amp;ドロップ]** にドロップします。
   * **[!UICONTROL 参照]** を選択し、コンピューターまたはネットワークからファイルを選択します。

   ファイルのコンテンツの **[!UICONTROL スキーマプレビュー]** が表示されます。 プレビューには、ファイルのデータ列が表示されます。 列のサイズを変更するには、「![ChevronDownSize300](/help/assets/icons2/ChevronDownSize300.svg)」を選択し、「**[!UICONTROL 列のサイズ変更]**」を選択します。 列のサイズを変更できるハンドルが表示されます。

   列の分類セットで分類が定義されていない場合は、アラート ![ アラート ](/help/assets/icons/Alert.svg) が表示されます。 このアラートは、既存の分類スキーマセットに分類が存在せず、読み込み時に作成されることを説明します。

1. **[!UICONTROL 競合時にデータを上書きしますか？現在の分類データを、新しく読み込んだデータで上書きするかどうかを]** します。 例：

   | | キー | 現在の製品カラー | ファイルを読み込み | 新しい製品カラー |
   |---|---|---|---|---|
   | ![SelectBox](/help/assets/icons/SelectBox.svg)**[!UICONTROL 競合時にデータを上書きしますか？]** | 1234 | 緑 | 青 | 青 |
   | ![Square](/help/assets/icons2/Square.svg)**[!UICONTROL 競合時にデータを上書きしますか？]** | 1234 | 緑 | 青 | 緑 |

1. 「**[!UICONTROL 適用]**」を選択します。列が既存のスキーマセットに分類として存在しない場合、アラートが表示されます。 これらの列は、アップロードを確定すると、新しい分類として追加されます。

   ![ 分類セット – 分類アラートのアップロード ](assets/classification-sets-schema-upload-file-preview-alert.png)

   「**[!UICONTROL アップロードを確認]**」を選択して、アップロードを確定します。 **[!UICONTROL アップロードをキャンセル]** を選択して、アップロードをキャンセルします。


### ダウンロード

分類データをダウンロードするには、「![ ダウンロード ](/help/assets/icons/Download.svg)**[!UICONTROL ダウンロード]**」を選択します。

![ 分類セット – スキーマのダウンロード分類データ ](assets/classification-sets-schema-download-file.png)

**[!UICONTROL 分類セット名 _のデータをダウンロード_]**ダイアログで、

1. ダウンロードする **[!UICONTROL 行]** の数を入力します。 例：`10000`。
1. 分類データの行をダウンロードする期間を選択するには、「**[!UICONTROL 次の期間に受信した行をダウンロード]**」に開始データと終了データを入力します。 または ![ カレンダー ](/help/assets/icons/Calendar.svg) を使用して、カレンダーポップアップを使用して期間を選択します。
1. 返すデータを選択するには、「返されるデータ **[!UICONTROL からオプションを選択し]** す。

   * **[!UICONTROL すべての値]** 現在の分類データのすべての値を返します。
   * **[!UICONTROL すべての列が空です]** 既存の分類データのキー値を含む列を返します。 値が存在しない分類データの、値のない列。
   * **[!UICONTROL すべての列が空]** 既存の分類データの値を含むキー列を返します。 分類データの値を持たない列。
1. ダウンロードした分類データの [ ファイル形式 ](/help/components/classifications/sets/data-files.md#general-file-requirements) を選択するには、**[!UICONTROL ファイル形式]** ドロップダウンメニューからオプションを選択します。 オプションは次のとおりです。

   * **[!UICONTROL JSON]**。
   * **[!UICONTROL コンマ区切り値]** （CSV）
   * **[!UICONTROL Excel タブ区切り値]** （TSV または TAB）。

1. ファイルのダウンロード時に使用する [ ファイルエンコーディング ](/help/components/classifications/sets/data-files.md#general-file-requirements) を選択するには、「ファイルエンコーディング」ドロップダウンメニューからオプションを選択します。 オプションは次のとおりです。

   * **[!UICONTROL UTF-8]**。
   * **[!UICONTROL Latin-1]**。


1. 「**[!UICONTROL ダウンロード]**」を選択して、分類データをダウンロードします。 ダウンロードしたファイルは、ブラウザーのデフォルトのダウンロードディレクトリにあります。ファイルのタイトルは「<code><i> 分類セット </i> です。<i>json</i>|<i>csv</i>|<i>tsv</i></code>。ファイルが既に存在する場合は、シーケンス番号 <code> （<i>x</i>）</code> がファイル名に追加されます。<br/> データを返さないオプションを指定した場合は、日付範囲と返されるデータのオプションを変更するように通知する **[!UICONTROL 通知]** ダイアログが表示されます。


### テンプレート

分類データのテンプレートをダウンロードするには、「![ ドキュメントフラグメント ](/help/assets/icons/DocumentFragment.svg)**[!UICONTROL テンプレート]**」を選択します。

![ 分類セットスキーマ – テンプレートのダウンロード ](assets/classification-sets-schema-download-template.png)

**[!UICONTROL 分類セット名 _のテンプレートをダウンロード_]**ダイアログで、

1. ダウンロードした分類データの [ ファイル形式 ](/help/components/classifications/sets/data-files.md#general-file-requirements) を選択するには、**[!UICONTROL ファイル形式]** ドロップダウンメニューからオプションを選択します。 オプションは次のとおりです。

   * **[!UICONTROL コンマ区切り値]**。
   * **[!UICONTROL Excel タブ区切り値]**。

1. ファイルのダウンロード時に使用する [ ファイルエンコーディング ](/help/components/classifications/sets/data-files.md#general-file-requirements) を選択するには、「ファイルエンコーディング」ドロップダウンメニューからオプションを選択します。 オプションは次のとおりです。

   * **[!UICONTROL UTF-8]**。
   * **[!UICONTROL Latin-1]**。

1. 「**[!UICONTROL ダウンロード]**」を選択して、分類データテンプレートをダウンロードします。 ダウンロードしたファイルは、ブラウザーのデフォルトのダウンロードディレクトリにあります。タイトルは <code><i> 分類セット </i> です。<i>csv</i>|<i>tsv</i></code>。ファイルが既に存在する場合は、シーケンス番号 <code> （<i>x</i>）</code> がファイル名に追加されます。


### 自動化 {#automate}


>[!CONTEXTUALHELP]
>id="classificationsets_schema_automate_locationaccount"
>title="場所のアカウント"
>abstract="分類データのインポートをサポートするアカウントタイプの場所アカウントのリスト。 **[!UICONTROL 新しいアカウント]** を選択して、新しい場所アカウントを作成します。"
>additional-url="https://experienceleague.adobe.com/docs/analytics/components/locations/configure-import-accounts.html?lang=en" text="クラウドのインポートおよびエクスポートアカウントの設定"


>[!CONTEXTUALHELP]
>id="classificationsets_schema_automate_location"
>title="場所"
>abstract="分類データのインポートをサポートする、選択した場所アカウントでの場所のリスト。 **[!UICONTROL 新しい場所]** を選択して、新しい場所を作成します。"
>additional-url="https://experienceleague.adobe.com/docs/analytics/components/locations/configure-import-locations.html?lang=en" text="クラウドの読み込み場所と書き出し場所の設定"

クラウドアカウントとクラウドの場所を設定および使用することで、分類データの取り込みを自動化できます。



>[!IMPORTANT]
>クラウドアカウントからの分類の取り込みを自動化するには、（またはネットワーク管理者が） IP アドレス範囲を指定して、がデータをネットワークに取り込める必要があります。 使用する Analytics データセンターの場所に応じて、1 つ以上の IP アドレス範囲を設定します。
>
>| Analytics データセンターの場所 | この IP アドレス範囲をネットワーク内の許可リストに追加します。 |
>|---|---:|
>| 太平洋北西部 | `52.254.104.0/22` |
>| ロンドン | `51.138.16.0/22` |
>| シンガポール | `20.40.0.0/14 ` |
>

分類の取り込みを自動化するには、「![ 歯車 ](/help/assets/icons/Gear.svg) **[!UICONTROL 自動化]**」を選択します。

![ 分類セットスキーマ – 自動化 ](assets/classification-sets-schema-automate.png)

**[!UICONTROL 分類セット名 _ダイアログの_]**取り込み場所を関連付ける/更新」ダイアログで、

1. クラウドの場所を選択するには、**[!UICONTROL 場所アカウント]** からオプションを選択します。 [ 分類データの読み込みを許可する、サポートされているアカウントタイプの場所アカウント ](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts) のみが表示されます。 新しいアカウントを作成するには、「**[!UICONTROL 新しいアカウント]**」を選択します。
1. 場所を選択するには、**[!UICONTROL 場所]** からオプションを選択します。 分類データのインポート用に選択した勘定科目タイプの場所のみが表示されます。 新しい場所を作成するには、「**[!UICONTROL 新しい場所]**」を選択します。

   >[!IMPORTANT]
   >
   >作成または選択する場所には、分類データファイルをホストする **[!UICONTROL バケット]** 内に **[!UICONTROL プレフィックス]** （フォルダー）を含める必要があります。 例えば、`files` という名前のフォルダーです。 バケットのルートでのファイルのホスティングは、ほとんどのクラウドの場所では機能しません。
   >

1. 区切り文字を選択するには、「**[!UICONTROL リスト区切り]**」ドロップダウンメニューからオプションを選択します。 次のオプションがあります。
   * **[!UICONTROL コンマ，]**
   * **[!UICONTROL セミコロン ;]**
   * **[!UICONTROL コロン :]**
   * **[!UICONTROL 縦棒グラフ |]**
   * **[!UICONTROL スペース]**
   * **[!UICONTROL タブ]**
1. ファイルのダウンロード時に [ ファイルエンコーディング ](/help/components/classifications/sets/data-files.md#general-file-requirements) を選択するには、**[!UICONTROL ファイルエンコーディング]** ドロップダウンメニューからオプションを選択します。 オプションは次のとおりです。

   * **[!UICONTROL UTF-8]**。
   * **[!UICONTROL Latin-1]**。

1. 取り込みジョブの完了をユーザーに通知するには、**[!UICONTROL 個のメール （取り込みジョブの完了時に通知する） （コンマ区切り）]** をコンマで区切ってメールアドレスを入力します。
1. 「**[!UICONTROL 検証]**」を選択します。 クラウドの場所への接続が検証されます。
1. 検証が成功すると、![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)**[!UICONTROL Location の検証が成功したことを示すトーストメッセージが表示されます。 クラウドストレージへの接続が確認されました。]**<br/> クラウド接続への接続を作成した場合は、「**[!UICONTROL  保存 ]**」を選択します。 それ以外の場合は、「**[!UICONTROL  更新 ]**」を選択します。 または、「**[!UICONTROL  キャンセル ]**」を選択して、クラウドの場所の設定をキャンセルします。

クラウドの場所にファイルをアップロードすると、15 分以内にファイルが検出され、読み込みジョブとして送信されます。 そのインポートジョブの結果は、[ 分類ジョブマネージャー ](/help/components/classifications/sets/job-manager.md) にレポートされます。 取り込みジョブの完了を通知するユーザーのリストに追加された場合は、メールメッセージも届きます。

例：

![ 分類セット – ジョブ検証メール ](assets/job-failed-validation.png){width="400"}


## アクションバー

アクションバーには、選択した分類で使用可能なアクションが表示されます。 利用可能なオプションは次のとおりです。

| アイコン | アクション | 説明 |
|---|---|---|
| ![参照](/help/assets/icons/Browse.svg) | **[!UICONTROL ルックアップの追加]** | 分類セットをルックアップ（サブ分類）として追加します。<br/> 添付 **[!UICONTROL 参照]** テーブルで、次の操作を行います。 <ol><li>**[!UICONTROL 分類名]** ドロップダウンメニューからルックアップ分類を選択します。</li><li>「**[!UICONTROL 追加]**」を選択します。</li></ol>ルックアップ分類が分類に追加され、内部 ID を使用して **[!UICONTROL 分類者]** 列にリストされます。 |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | **[!UICONTROL ルックアップを削除]** | 分類セットをルックアップとして削除します。 分類からルックアップを完全に削除するには、**[!UICONTROL 分類セット _から_ 分類 _確認ダイアログの_]**削除&#x200B;**[!UICONTROL を選択します]**。 |
| ![名前変更](/help/assets/icons/Rename.svg) | **[!UICONTROL 名前変更]** | 分類の **[!UICONTROL 分類名]** の名前を変更します。 **[!UICONTROL 名前を変更：_分類名_]**ダイアログで、新しい名前を入力して&#x200B;**[!UICONTROL 名前を変更]**を選択します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 分類を削除します。 **[!UICONTROL 分類名を削除 _ダイアログが表示され_]**す。 分類を削除するには、「**[!UICONTROL 削除]**」を選択します。 |
