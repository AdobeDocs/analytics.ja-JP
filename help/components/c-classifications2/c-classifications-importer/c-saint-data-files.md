---
description: インポーターを使用すると、分類データを Analytics レポートに一括してファイルでアップロードできます。データのアップロードを正常に行うために、インポートでは指定のファイル形式を使用する必要があります。
seo-description: インポーターを使用すると、分類データを Analytics レポートに一括してファイルでアップロードできます。データのアップロードを正常におこなうために、インポートでは指定のファイル形式を使用する必要があります。
seo-title: 分類データファイル
solution: Analytics
subtopic: '分類      '
title: 分類データファイル
topic: 管理ツール
uuid: f27bb812-56e0-472a-9993- d869f0fea700
translation-type: tm+mt
source-git-commit: c0c4a3f42a7236c6f9e5001f5ca0ef9173dbaa66

---


# 分類データファイル

インポーターを使用すると、分類データを Analytics レポートに一括してファイルでアップロードできます。データのアップロードを正常に行うために、インポートでは指定のファイル形式を使用する必要があります。

有効なデータファイルを作成するために、テンプレートファイルをダウンロードして、このテンプレートのファイル構造に分類データを貼り付けることができます。詳しくは、 [分類テンプレートのダウンロード](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).

See [General File Structure](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9EFF968DF5D244A887DE94075431C1BE) for more information about character limits in classifications.

See [Numeric 2 Classifications](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) for information about uploading data using numeric 2 classifications.

## 一般的なファイル構造

データファイルの例を以下に示します。

![](assets/completed-saint-file.png)

データファイルは、以下の構造ルールに従って作成する必要があります。

* 分類は、0（ゼロ）の値を持つことはできません。
* インポートおよびエクスポートする列の数を 30 以内にすることをお勧めします。
* アップロードするファイルは、BOM なしの UTF-8 でエンコードする必要があります。
* タブ、改行、引用符などの特殊文字は、バージョン 2.1 のファイル形式が指定されており、セルが適切に[エスケープ](../../../components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md#task_EB47E80063F14F9CB2D186C0CAA9CBAD)されている場合にのみ使用することができます。特殊文字には、次のものがあります。

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   コンマは特殊文字に含まれません。

* キャレット（^）は、下位分類を示すために使用されるので、分類にこの文字を含めることはできません。
* ハイフンを使用する際は注意が必要です。例えば、Social のキーワードでハイフン（-）を使用すると、Social はハイフンを [!DNL Not] 演算子（マイナス記号）として認識します。For example, if you specify *`fragrance-free`* as a term using the import, Social recognizes the term as fragrance *`minus`* free and collects posts that mention *`fragrance`*, but not *`free`*.
* レポートデータの分類では、文字数の制限が適用されます。For example, if you upload a classifications text file for products ( *`s.products`*) with product names longer than 100 characters (bytes), the products will not display in reporting. トラッキングコードおよびすべてのカスタムコンバージョン変数（eVar）では、255 バイトを使用できます。
* タブ区切りのデータファイルにします（スプレッドシートアプリケーションやテキストエディターを使用してテンプレートファイルを作成します）。
* Either a [!DNL .tab] or [!DNL .txt] file extension.
* シャープ記号（#）でコメントを記述できます。# で始まる行は無視されます。
* 2 つのシャープ記号の後に SC が続く（## SC）場合は、レポーティングで使用される前処理ヘッダーコメントの行を示します。この行は削除しないでください。
* 分類エクスポートでは、キーに改行文字が含まれているためにキーが重複することがあります。FTP またはブラウザーのエクスポートで、FTP アカウントに対して引用符の使用を有効にすることで、この問題を解決できます。引用符の使用を有効にすると、改行文字が含まれている各キーが引用符で囲まれます。
* インポートファイルの先頭行のセル C1 には、ファイルの残りの部分で分類が引用符の使用をどのように処理するかを判別するバージョン ID が格納されます。

   * v2.0 は引用符を無視し、すべてが指定されたキーと値の一部であると見なします。例えば、"This is ""some value""" という値を考えてみましょう。v2.0 は、これを文字どおりに "This is ""some value""" と解釈します。
   * v2.1 は、引用符が Excel ファイルで使用されているファイルフォーマットの一部であると見なすよう分類に指示します。したがって、v2.1 は上記の例を This is "some value" にフォーマットします。
   * ファイル内で v2.1 が指定されているが実際には v2.0 が必要な場合、つまり、Excel のフォーマットとしては不正な方法で引用符が使用されている場合は、問題が生じることがあります。例えば、"VP NO REPS" S/l Dress w/ Overlay という値があるとします。v2.1 では、これは正しくないフォーマットであり（値は開始引用符と終了引用符で囲み、実際の値の一部である引用符は引用符でエスケープする必要があります）、これ以降の行は分類処理がおこなわれません。
   * ファイルのヘッダー（セル C1）を変更してファイル形式を v2.0 に変更するか、ファイル全体で Excel の引用符を正しく使用してください。

* データファイルの最初にある（コメントなしの）行には、列内の分類データを示す列見出しが含まれます。列見出しには、特定の形式を使用する必要があります。詳しくは、[列見出しの形式](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_ADC08C783477451B959782CEA23AF5EF)を参照してください。
* データファイルのヘッダー行のすぐ後には、データ行が続きます。データの各行には、列見出しごとに 1 つのデータフィールドを含める必要があります。
* データファイルでは、以下の制御コードがサポートされます。このコードは、ファイルを構造化し、分類データを正確にインポートするために使用されます。

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制御コード </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;改行&gt; </p> </td> 
   <td colname="col2"> <p>データファイルのデータ行／レコード間の区切りとしてサポートされているのは、改行文字だけです。通常は、データファイルの自動生成プログラムを記述するときに、具体的にこれらの文字を挿入する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>自動的にこのエレメントの一意の ID が生成されます。 </p> <p>キャンペーン用途の場合は、この制御値によってクリエイティブエレメントごとに ID が割り当てられます。詳しくは、 <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443" format="dita" scope="local"> キー </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>該当する列は日付範囲を表す文字列であることをシステムに伝えます。詳しくは、 <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9ECCD5ED97764CDC90C0B7B0F9461825" format="dita" scope="local"> Date </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空のフィールド </p> </td> 
   <td colname="col2"> <p>価が NULL であることを示します。特定のデータ列が現在のレコードに適用されない場合に使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER 修飾子 </p> </td> 
   <td colname="col2"> <p>データ列が <span class="wintitle">PER 修飾子</span>のフィールドを示すことを指定します。<a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_7E199A26E3274B31B07CCAF8DFE3B274" format="dita" scope="local"> PER修飾子の見出しを </a>参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [一般的なアップロードの問題](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## 列見出し形式

>[!NOTE]
>
>インポートおよびエクスポートする列の数を 30 以内にすることをお勧めします。

分類ファイルは次の列見出しをサポートしています。

### キー

各値はシステム全体で一意である必要があります。The value in this field corresponds to a value assigned to the [!DNL Analytics] variable in your Web site’s [!DNL JavaScript] beacon. Data in this column might include ~autogen~ or any other unique tracking code.

### 分類列の見出し

例えば、Reports &amp; Analytics では、[!UICONTROL キャンペーン]変数は「[!UICONTROL キャンペーン]」および「[!UICONTROL クリエイティブエレメント]」の 2 つに自動的に分類されます。データを「[!UICONTROL キャンペーン]」の分類に追加するために、分類データファイルの列見出しを「[!UICONTROL キャンペーン]」にします。

>[!NOTE]
>
>[!UICONTROL 分類] 列の見出しの値は、分類の命名規則と完全に一致する必要があります。または、インポートに失敗します。例えば、管理者が[!UICONTROL キャンペーン設定マネージャー]で分類名を「[!UICONTROL キャンペーン]」から「[!UICONTROL 内部キャンペーン名]」に変更した場合は、ファイルの列見出しを同様に変更する必要があります。

また、データファイルでは、以下に示す見出しの規則をサポートし、下位分類やその他の特殊なデータ列を識別します。

### 下位分類の見出し

例えば、「[!UICONTROL Campaigns^Owner]」は[!UICONTROL キャンペーン所有者]の値を含む列の見出しです。同様に、「[!UICONTROL Creative Elements^Size]」は[!UICONTROL クリエイティブエレメント]分類の下位分類である[!UICONTROL サイズ]を含む列の見出しです。

### 分類指標の見出し

例えば、「[!UICONTROL Campaigns^~Cost]」は[!UICONTROL キャンペーン]分類の[!UICONTROL コスト]指標を示します。

### PER修飾子の見出し

*`Per Modifier`* 見出しは、分類指標の見出し *`~per`* に追加して示します。For example, if the *`Metric`* heading is *`Campaigns^~Cost`*, the PER modifier heading is *`Campaigns^~Cost~per`*. Adobe supports the following *`PER Modifier`* keywords:

これらの文字は、データファイルで特別な意味を持ちます。可能な限り、これらの語句を属性名やデータ内で使用しないでください。

**FIXED：**&#x200B;固定値。値の増減は行われません。

**DAY：**&#x200B;値に、レポート内の日数を掛けます。

**ORDER：**&#x200B;値に、レポート内の行項目の注文件数を掛けます。

**CHECKOUT：**&#x200B;値に、レポート内の行項目のチェックアウト数を掛けます。

**UNIT：**&#x200B;値に、レポート内の行項目の数量を掛けます。

**REVENUE：**&#x200B;値に、レポート内の行項目の売上高を掛けます。

**SCADD：**&#x200B;値に、レポート内の行項目ごとに[!UICONTROL 買い物かごの追加]イベントが呼び出された回数を掛けます。

**SCREMOVE：**&#x200B;値に、レポート内の行項目ごとに[!UICONTROL 買い物かごの削除]イベントが呼び出された回数を掛けます。

**INSTANCE：**&#x200B;値に、レポート内の行項目のインスタンス数を掛けます。

**CLICK：**&#x200B;値に、レポート内の行項目のクリック数を掛けます。

**EVENT：**&#x200B;値に、レポート内の行項目ごとに指定されたカスタムイベントが発生した回数を掛けます。

**例:** キャンペーンAのコスト$10,000の場合、 [!UICONTROL "Campaigns^~ Cost] »列には10000の値が含まれ、?«Campaigns^ ?Costper??[!UICONTROL ~~]レポートにキャンペーン A のコストを表示するとき、日付範囲に対応するキャンペーン A の固定コストとして $10,000 が表示されます。

**例:** キャンペーンBのコストがクリックあたりおよそ$2である場合、 [!UICONTROL "Campaigns^~ Cost] »列には2が含まれ、??«Campaigns^?~ Cost???**[!UICONTROL ~~]**When displaying the Cost for Campaign B in the reports, Adobe calculates (2 * [number of clicks]) on the fly for the date range of the report. これにより、キャンペーン B でのクリック数に基づいて合計コストを計算できます。

### 日付

通常、キャンペーンの日付は個別のキャンペーンに関連付けられた範囲（開始日と終了日）になります。日付は YYYY/MM/DD の形式で示す必要があります。例えば、「2013/06/15-2013/06/30」とします。

詳しくは、[コンバージョン分類](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications)を参照してください。

>[!NOTE]
>
>In the May 10, 2018, [!DNL Analytics] Maintenance release, Adobe started to limit the functionality of date-enabled and numeric classifications. これらの分類タイプは、管理者および分類インポーターの各インターフェイスから削除されました。新しい日付が有効な分類および数値の分類は追加できません。既存の分類は、通常の分類ワークフローで引き続き管理（アップロード、削除）でき、レポートで使用できます。

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL 分類] を使用すると、キャンペーンまたはその他のコンバージョン [!UICONTROL 分類]に日付範囲を割り当てることができ、より正確なキャンペーン測定を行うことができます。値の日付範囲を指定した場合は、値が一致しても、日付範囲外で発生するものは分類されません。これは、キャンペーン自体に一致するすべてのヒットを測定するのではなく、キャンペーンが実施されていた正確な日付を利用してキャンペーンを測定する場合に役立ちます。日付範囲を使用して値を分類するには、次の条件を満たす必要があります。

* [!UICONTROL 分類] は、コンバージョン変数に基づいている必要があります。
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* 指定する日付範囲には、開始日および（オプションで）終了日が含まれている必要があります。

日付範囲に基づいてキャンペーンを分類するには：

1. Log in to [!DNL Analytics] and go to Admin &gt; Classifications.
1. 「**[!UICONTROL ブラウザエクスポート]」タブをクリックし、日付が有効な分類の設定が正しいことを確認して、「ファイルのエクスポート」をクリックします。**
1. このファイルを Microsoft Excel、またはその他の使い慣れているスプレッドシートエディターで開きます。
1. いずれかの列が

   ^~period~
which is the column to enter the date range in.
1. この列に、各値の日付範囲を

   `YYYY/MM/DD - YYYY/MM/DD`をインストールします。次の規則に従ってください。

   * ダッシュの両端にスペースを挿入します。
   * 範囲を区切る文字として半角のハイフン（-）を使用します。en ダッシュ（–）や em ダッシュ（—）は使用しないでください。
   * 月や日付が 1 桁の場合は、前にゼロを付加します。
   * 日付範囲の開始日は必ず指定します。終了日はオプションです。

1. Save the file, and upload it to [!DNL Analytics] by going to Admin | Classifications | Import File.

>[!NOTE]
>
>特定のキー値に複数の日付範囲を設定することはできません。

## 分類のトラブルシューティング

* [一般的な のアップロードの問題](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)：不適切なファイル形式およびファイルの内容に起因する問題について説明したナレッジベース記事です。

