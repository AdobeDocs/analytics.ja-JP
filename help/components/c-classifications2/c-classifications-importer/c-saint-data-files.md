---
description: インポーターを使用すると、分類データを Analytics レポートに一括してファイルでアップロードできます。データのアップロードを正常におこなうために、インポートでは指定のファイル形式を使用する必要があります。
subtopic: Classifications
title: 分類データファイル
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 分類データファイル

インポーターを使用すると、分類データを Analytics レポートに一括してファイルでアップロードできます。データのアップロードを正常におこなうために、インポートでは指定のファイル形式を使用する必要があります。

有効なデータファイルを作成するために、テンプレートファイルをダウンロードして、このテンプレートのファイル構造に分類データを貼り付けることができます。詳しくは、[分類テンプレートのダウンロード](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md)を参照してください。

分類での文字数制限について詳しくは、[一般的なファイル構造](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)を参照してください。

数値 2 分類を使用したデータのアップロードについて詳しくは、[数値 2 分類](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md)を参照してください。

## 一般的なファイル構造

データファイルの例を以下に示します。

![](assets/completed-saint-file.png)

データファイルは、以下の構造ルールに従って作成する必要があります。

* 分類は、0（ゼロ）の値を持つことはできません。
* インポートおよびエクスポートする列の数を 30 以内にすることをお勧めします。
* アップロードするファイルは、BOM なしの UTF-8 でエンコードする必要があります。
* タブ、改行、引用符などの特殊文字は、バージョン 2.1 のファイル形式が指定されており、セルが適切に[エスケープ](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md)されている場合にのみ使用することができます。特殊文字には、次のものがあります。

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   コンマは特殊文字に含まれません。

* キャレット（^）は、下位分類を示すために使用されるので、分類にこの文字を含めることはできません。
* ハイフンを使用する際は注意が必要です。例えば、Social のキーワードでハイフン（-）を使用すると、Social はハイフンを [!DNL Not] 演算子（マイナス記号）として認識します。例えば、読み込むキーワードとして「*`fragrance-free`*」を指定すると、Social はこのキーワードを「fragance *`minus`* free」と認識し、「*`fragrance`*」に関する投稿のみを収集し、「*`free`*」に関する投稿は収集されません。
* レポートデータの分類では、文字数の制限が適用されます。例えば、製品名が 100 文字（バイト）を超える製品の分類テキストファイル（*`s.products`*）をアップロードしても、製品はレポートに表示されません。トラッキングコードおよびすべてのカスタムコンバージョン変数（eVar）では、255 バイトを使用できます。
* タブ区切りのデータファイルにします（スプレッドシートアプリケーションやテキストエディターを使用してテンプレートファイルを作成します）。
* ファイルの拡張子は、[!DNL .tab] または [!DNL .txt] にします。
* シャープ記号（#）でコメントを記述できます。# で始まる行は無視されます。
* 2 つのシャープ記号の後に SC が続く（## SC）場合は、レポーティングで使用される前処理ヘッダーコメントの行を示します。この行は削除しないでください。
* 分類エクスポートでは、キーに改行文字が含まれているためにキーが重複することがあります。FTP またはブラウザーのエクスポートで、FTP アカウントに対して引用符の使用を有効にすることで、この問題を解決できます。引用符の使用を有効にすると、改行文字が含まれている各キーが引用符で囲まれます。
* インポートファイルの先頭行のセル C1 には、ファイルの残りの部分で分類が引用符の使用をどのように処理するかを判別するバージョン ID が格納されます。

   * v2.0 は引用符を無視し、すべてが指定されたキーと値の一部であると見なします。例えば、&quot;This is &quot;&quot;some value&quot;&quot;&quot; という値を考えてみましょう。v2.0 は、これを文字どおりに &quot;This is &quot;&quot;some value&quot;&quot;&quot; と解釈します。
   * v2.1 は、引用符が Excel ファイルで使用されているファイルフォーマットの一部であると見なすよう分類に指示します。したがって、v2.1 は上記の例を This is &quot;some value&quot; にフォーマットします。
   * ファイル内で v2.1 が指定されているが実際には v2.0 が必要な場合、つまり、Excel のフォーマットとしては不正な方法で引用符が使用されている場合は、問題が生じることがあります。例えば、&quot;VP NO REPS&quot; S/l Dress w/ Overlay という値があるとします。v2.1 では、これは正しくないフォーマットであり（値は開始引用符と終了引用符で囲み、実際の値の一部である引用符は引用符でエスケープする必要があります）、これ以降の行は分類処理がおこなわれません。
   * ファイルのヘッダー（セル C1）を変更してファイル形式を v2.0 に変更するか、ファイル全体で Excel の引用符を正しく使用してください。

* データファイルの最初にある（コメントなしの）行には、列内の分類データを示す列見出しが含まれます。列見出しには、特定の形式を使用する必要があります。詳しくは、[列見出しの形式](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)を参照してください。
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
   <td colname="col2"> <p>自動的にこのエレメントの一意の ID が生成されます。 </p> <p>キャンペーン用途の場合は、この制御値によってクリエイティブエレメントごとに ID が割り当てられます。Keyを参照し <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > てくだ </a>さい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>該当する列は日付範囲を表す文字列であることをシステムに伝えます。日付を参 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > 照してくだ </a>さい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空のフィールド </p> </td> 
   <td colname="col2"> <p>価が NULL であることを示します。特定のデータ列が現在のレコードに適用されない場合に使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER 修飾子 </p> </td> 
   <td colname="col2"> <p>データ列が <span class="wintitle">PER 修飾子</span>のフィールドを示すことを指定します。<a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  >PER 修飾子の見出し</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [一般的な のアップロードの問題](https://helpx.adobe.com/jp/analytics/kb/common-saint-upload-issues.html)


## 列見出しの形式

>[!NOTE]インポートおよびエクスポートする列の数を 30 以内にすることをお勧めします。

分類ファイルは次の列見出しをサポートしています。

### キー

各値はシステム全体で一意である必要があります。このフィールドの値は、Web サイトの [!DNL JavaScript] ビーコンで [!DNL Analytics] の変数に割り当てられた値に対応しています。この列のデータには、~autogen~ や一意のトラッキングコードが含まれる場合があります。

### 分類列の見出し

例えば、Reports &amp; Analyticsでは、変数に対して次の2つの分類が自動的に含ま [!UICONTROL Campaign] れます。 [!UICONTROL Campaigns] と [!UICONTROL Creative Elements]To add data to the [!UICONTROL Campaigns] classification, the column heading in the classification data file would be [!UICONTROL Campaigns].

>[!NOTE] 列見出しの値は、分 [!UICONTROL Classifications] 類の命名規則と完全に一致する必要があります。一致しない場合、インポートは失敗します。 例えば、管理者がに変更した場 [!UICONTROL Campaigns] 合は、フ [!UICONTROL Internal Campaign Names] ァイ [!UICONTROL Campaign Set-up Manager]ルの列見出しが一致するように変更する必要があります。

また、データファイルでは、以下に示す見出しの規則をサポートし、下位分類やその他の特殊なデータ列を識別します。

### 下位分類の見出し

For example, [!UICONTROL Campaigns^Owner] is a column heading for the column containing [!UICONTROL Campaign Owner] values. Similarly, [!UICONTROL Creative Elements^Size] is a column heading for the column containing the [!UICONTROL Size] sub-classification of the [!UICONTROL Creative Elements] classification.

### 分類指標の見出し

For example, [!UICONTROL Campaigns^~Cost] refers to the [!UICONTROL Cost] metric in the [!UICONTROL Campaigns] classification.

### PER 修飾子の見出し

*`Per Modifier`* の見出しは、分類指標の見出しに *`~per`* を付加して示します。例えば、*`Metric`*&#x200B;の見出しが「*`Campaigns^~Cost`*」の場合、PER 修飾子の見出しは「*`Campaigns^~Cost~per`*」になります。アドビでは、次の *`PER Modifier`* キーワードをサポートしています。

これらの文字は、データファイルで特別な意味を持ちます。可能な限り、これらの語句を属性名やデータ内で使用しないでください。

**FIXED：**&#x200B;固定値。値の増減は行われません。

**DAY：**&#x200B;値に、レポート内の日数を掛けます。

**ORDER：**&#x200B;値に、レポート内の行項目の注文件数を掛けます。

**CHECKOUT：**&#x200B;値に、レポート内の行項目のチェックアウト数を掛けます。

**UNIT：**&#x200B;値に、レポート内の行項目の数量を掛けます。

**REVENUE：**&#x200B;値に、レポート内の行項目の売上高を掛けます。

**SCADD:** 値に、レポート内の行項目ごとに [!UICONTROL Shopping Cart Add] イベントが呼び出された回数を掛けます。

**SCREMOVE:** 値に、レポート内の行項目ごとに [!UICONTROL Shopping Cart Remove] イベントが呼び出された回数を掛けます。

**INSTANCE：**&#x200B;値に、レポート内の行項目のインスタンス数を掛けます。

**CLICK：**&#x200B;値に、レポート内の行項目のクリック数を掛けます。

**EVENT：**&#x200B;値に、レポート内の行項目ごとに指定されたカスタムイベントが発生した回数を掛けます。

**例：** キャンペーンAのコストが$10,000の場合、 [!UICONTROL Campaigns^~Cost] 列の値は10,000で、コスパー列の値 [!UICONTROL Campaigns^~~は] 10,000です [!UICONTROL FIXED]。 レポートにキャンペーン A のコストを表示すると、日付範囲に対応するキャンペーン A の固定コストとして $10,000 が表示されます。

**例：** キャンペーンBのコストがクリックあたり約2ドルの場合、列には2が含 [!UICONTROL Campaigns^~Cost] まれ、コストパー列には **[!UICONTROL Campaigns^~~が含ま]** れま [!UICONTROL CLICK]す。 レポートにキャンペーン B のコストを表示するとき、レポートの日付範囲に対応する、その時点の「2 * [クリック数]」が計算されます。これにより、キャンペーン B でのクリック数に基づいて合計コストを計算できます。

### 日付

通常、キャンペーンの日付は個別のキャンペーンに関連付けられた範囲（開始日と終了日）になります。日付は YYYY/MM/DD の形式で示す必要があります。例えば、「2013/06/15-2013/06/30」とします。

詳しくは、[コンバージョン分類](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html)を参照してください。

>[!NOTE]2018 年 5 月 10 日[!DNL Analytics]の Analytics メンテナンスリリースにおいて、日付が有効な分類と数値の分類の機能制限を開始しました。これらの分類タイプは、管理者および分類インポーターの各インターフェイスから削除されました。新しい日付が有効な分類および数値の分類は追加できません。既存の分類は、通常の分類ワークフローで引き続き管理（アップロード、削除）でき、レポートで使用できます。

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Classifications] を使用して、日付範囲をキャンペーンや他のコンバージョンに割り当てることができ、より正確 [!UICONTROL classifications]なキャンペーン測定が可能です。 値の日付範囲を指定した場合は、値が一致しても、日付範囲外で発生するものは分類されません。これは、キャンペーン自体に一致するすべてのヒットを測定するのではなく、キャンペーンが実施されていた正確な日付を利用してキャンペーンを測定する場合に役立ちます。日付範囲を使用して値を分類するには、次の条件を満たす必要があります。

* The [!UICONTROL classification] must be based on a conversion variable.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* 指定する日付範囲には、開始日および（オプションで）終了日が含まれている必要があります。

日付範囲に基づいてキャンペーンを分類するには：

1. [!DNL Analytics] にログインし、管理者／分類に移動します。
1. Click the **[!UICONTROL Browser Export]** tab, ensure the settings to your date-enabled classification are correct, then click Export File.
1. このファイルを Microsoft Excel、またはその他の使い慣れているスプレッドシートエディターで開きます。
1. 列の 1 つが

   ^~period~ で終わり、日付範囲を入力する列であることを示します。
1. この列に、各値の日付範囲を

   `YYYY/MM/DD - YYYY/MM/DD`をインストールします。次の規則に従ってください。

   * ダッシュの両端にスペースを挿入します。
   * 範囲を区切る文字として半角のハイフン（-）を使用します。en ダッシュ（–）や em ダッシュ（—）は使用しないでください。
   * 月や日付が 1 桁の場合は、前にゼロを付加します。
   * 日付範囲の開始日は必ず指定します。終了日はオプションです。

1. ファイルを保存し、管理者／分類／ファイルのインポートに移動して [!DNL Analytics] にアップロードします。

>[!NOTE]キー値に対して、複数の日付範囲は指定できません。

## 分類のトラブルシューティング

* [一般的な のアップロードの問題](https://helpx.adobe.com/jp/analytics/kb/common-saint-upload-issues.html)：不適切なファイル形式およびファイルの内容に起因する問題について説明したナレッジベース記事です。

