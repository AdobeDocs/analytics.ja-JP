---
description: インポーターを使用すると、分類データをファイル内のAnalyticsレポートに一括アップロードできます。 データのアップロードを正常におこなうために、インポートでは指定のファイル形式を使用する必要があります。
subtopic: Classifications
title: 分類データファイル
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 分類データファイル

インポーターを使用すると、分類データをファイル内のAnalyticsレポートに一括アップロードできます。 データのアップロードを正常におこなうために、インポートでは指定のファイル形式を使用する必要があります。

有効なデータファイルを作成するために、分類データを貼り付けるファイル構造を提供するテンプレートファイルをダウンロードできます。 詳しくは、[分類テンプレートのダウンロード](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md)を参照してください。

分類での文字数制限について詳しくは、[一般的なファイル構造](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)を参照してください。

数値 2 分類を使用したデータのアップロードについて詳しくは、[数値 2 分類](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md)を参照してください。

## 一般的なファイル構造

次の図はサンプルデータファイルです。

![](assets/completed-saint-file.png)

データファイルは、次の構造ルールに従う必要があります。

* 分類の値を0（ゼロ）にすることはできません。
* インポートおよびエクスポートする列の数を 30 以内にすることをお勧めします。
* アップロードしたファイルは、BOMを含まないUTF-8文字エンコードを使用する必要があります。
* タブ、改行、引用符などの特殊文字は、v2.1ファイル形式が指定され、セルが正しくエスケープされている場合は、セル内に埋め込むことがで [きます](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md)。 特殊文字には、次のものがあります。

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   コンマは特殊文字ではありません。

* キャレット(^)は下位分類を表すために使用されるので、分類に含めることはできません。
* ハイフンを使用する場合は注意が必要です。 例えば、Social のキーワードでハイフン（-）を使用すると、Social はハイフンを [!DNL Not] 演算子（マイナス記号）として認識します。例えば、読み込むキーワードとして「*`fragrance-free`*」を指定すると、Social はこのキーワードを「fragance *`minus`* free」と認識し、「*`fragrance`*」に関する投稿のみを収集し、「*`free`*」に関する投稿は収集されません。
* レポートデータの分類では、文字数の制限が適用されます。例えば、製品名が 100 文字（バイト）を超える製品の分類テキストファイル（*`s.products`*）をアップロードしても、製品はレポートに表示されません。トラッキングコードおよびすべてのカスタムコンバージョン変数（eVar）では、255 バイトを使用できます。
* タブ区切りのデータファイルにします（スプレッドシートアプリケーションやテキストエディターを使用してテンプレートファイルを作成します）。
* ファイルの拡張子は、[!DNL .tab] または [!DNL .txt] にします。
* シャープ記号(#)は、行がユーザーコメントであることを示します。 #で始まる行は無視されます。
* 重複シャープ記号の後にSCが続く(## SC)場合、レポートで使用される前処理ヘッダーコメントの行を示します。 これらの行は削除しないでください。
* 分類のエクスポートでは、重複キーが使用される場合があります。キーに改行文字が含まれているためです。 FTPまたはブラウザーのエクスポートでは、FTPアカウントの引用符の使用を有効にすることで、この問題を解決できます。 これにより、各キーを引用符で囲み、改行文字を含めます。
* インポートファイルの最初の行のセルC1には、ファイルの残りの部分で分類が引用符の使用をどのように処理するかを決定するバージョン識別子が含まれます。

   * v2.0では引用符は無視され、すべてが指定されたキーと値の一部であると見なされます。 例えば、次の値を考えてみましょう。&quot;これは&quot;&quot;some value&quot;&quot;です。&quot; v2.0では、これを次のように解釈します。&quot;これは&quot;&quot;some value&quot;&quot;です。&quot;
   * v2.1は、引用符がExcelファイルで使用されるファイルの形式設定の一部であると見なすよう分類に指示します。 したがって、v2.1では、上の例を次のようにフォーマットします。これは「some value」です。
   * ファイル内でv2.1が指定されているが、実際に必要なのはv2.0である、つまり、Excelの書式設定では不正な方法で引用符が使用されている場合、問題が発生する可能性があります。 例えば、次の値がある場合、「VP NO REPS」 S/l Dress w/ Overlay。 v2.1では、この形式は正しくありません（値は開始引用符と終了引用符で囲み、実際の値の一部である引用符は引用符でエスケープする必要があります）。分類はこの時点を超えて機能しません。
   * 必ず、次のいずれかの操作を行います。アップロードするファイルのヘッダ（セルC1）を変更してファイル形式をv2.0に変更するか、ファイル全体でExcelの引用符を適切に実装します。

* データファイルの最初の（コメントなしの）行には、その列の分類データを識別する列見出しが含まれます。 列見出しには、特定の形式が必要です。 詳しくは、[列見出しの形式](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)を参照してください。
* データファイル内のヘッダー行のすぐ後に、データ行が続きます。 各行のデータには、各列見出しのデータフィールドを含める必要があります。
* このデータファイルは、次の制御コードをサポートしています。このコードは、ファイルの構造を提供し、分類データを正しく読み込むためにアドビが使用します。

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
   <td colname="col2"> <p>新しい行文字は、データファイル内のデータ行/レコード間の区切り文字としてサポートされている唯一の文字です。 通常、これらの文字は、データファイルを自動生成するプログラムを書き込む場合にのみ挿入します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>～autogen～ </p> </td> 
   <td colname="col2"> <p>この要素の一意のIDをアドビが自動的に生成するリクエスト。 </p> <p>キャンペーンコンテキストでは、この制御値によって、各クリエイティブエレメントに識別子を割り当てるようにアドビに指示されます。 Keyを参照し <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > てくだ </a>さい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>～period～ </p> </td> 
   <td colname="col2"> <p>データ列がアイテムに関連付けられた日付範囲を表すことを指定します。 日付を参 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > 照してくだ </a>さい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空のフィールド </p> </td> 
   <td colname="col2"> <p>現在のフィールドのNULL値を表します。 特定のデータ列が現在のレコードに適用されない場合に使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER修飾子 </p> </td> 
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

例えば、Reports &amp; Analyticsでは、変数に対して次の2つの分類が自動的に含ま [!UICONTROL Campaign] れます。 [!UICONTROL Campaigns] と [!UICONTROL Creative Elements]分類にデータを追加す [!UICONTROL Campaigns] る場合、分類データファイルの列見出しは次のようになりま [!UICONTROL Campaigns]す。

>[!NOTE] 列見出しの値は、分 [!UICONTROL Classifications] 類の命名規則と完全に一致する必要があります。一致しない場合、インポートは失敗します。 例えば、管理者がに変更した場 [!UICONTROL Campaigns] 合は、フ [!UICONTROL Internal Campaign Names] ァイ [!UICONTROL Campaign Set-up Manager]ルの列見出しが一致するように変更する必要があります。

また、このデータファイルでは、次の見出しの規則をサポートして、下位分類やその他の特殊なデータ列を識別します。

### 下位分類の見出し

例えば、は [!UICONTROL Campaigns^Owner] 値を含む列の列見出し [!UICONTROL Campaign Owner] です。 同様に、 [!UICONTROL Creative Elements^Size] は分類の副分類を含む列の列見 [!UICONTROL Size] 出しを示してい [!UICONTROL Creative Elements] ます。

### 分類指標の見出し

For example, [!UICONTROL Campaigns^~Cost] refers to the [!UICONTROL Cost] metric in the [!UICONTROL Campaigns] classification.

### PER 修飾子の見出し

*`Per Modifier`* の見出しは、分類指標の見出しに *`~per`* を付加して示します。例えば、*`Metric`*&#x200B;の見出しが「*`Campaigns^~Cost`*」の場合、PER 修飾子の見出しは「*`Campaigns^~Cost~per`*」になります。アドビでは、次の *`PER Modifier`* キーワードをサポートしています。

これらの文字は、データファイル内で特別な意味を持ちます。 可能な限り、これらの単語を属性名とデータで使用しないでください。

**修正：** 固定値。 拡大縮小は実行しません。

**日：** 値にレポート内の日数を掛けます。

**順序：** 値に、レポート内の行項目の注文数を掛けます。

**チェックアウト：** 値に、レポート内の行項目のチェックアウト数を掛けます。

**単位：** 値に、レポート内の行項目の数量を掛けます。

**売上高：** 値に、レポート内の行項目の売上高を掛けます。

**SCADD:** 値に、レポート内の行項目ごとに [!UICONTROL Shopping Cart Add] イベントが呼び出された回数を掛けます。

**SCREMOVE:** 値に、レポート内の行項目ごとに [!UICONTROL Shopping Cart Remove] イベントが呼び出された回数を掛けます。

**INSTANCE:** 値に、レポート内の行項目のインスタンス数を掛けます。

**クリック：** 値に、レポート内の行項目のクリック数を掛けます。

**イベント:** 値に、レポートの行項目ごとに指定したカスタムイベントが発生した回数を掛けます。

**例：** キャンペーンAのコストが$10,000の場合、 [!UICONTROL Campaigns^~Cost] 列の値は10,000で、コスパー列の値 [!UICONTROL Campaigns^~~は] 10,000です [!UICONTROL FIXED]。 レポートにキャンペーン A のコストを表示すると、日付範囲に対応するキャンペーン A の固定コストとして $10,000 が表示されます。

**例：** キャンペーンBのコストがクリックあたり約2ドルの場合、列には2が含 [!UICONTROL Campaigns^~Cost] まれ、コストパー列には **[!UICONTROL Campaigns^~~が含ま]** れま [!UICONTROL CLICK]す。 レポートにキャンペーン B のコストを表示するとき、レポートの日付範囲に対応する、その時点の「2 * [クリック数]」が計算されます。これにより、キャンペーン B でのクリック数に基づいて合計コストを計算できます。

### 日付

キャンペーンの日付は、通常、個々の開始に関連付けられた範囲(キャンペーンと終了日)です。 日付はYYYY/MM/DD形式で表示する必要があります。 例：2013/06/15-2013/06/30。

詳しくは、「コンバージョンの分類」を [参照してくださ](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications)い。

>[!NOTE]2018 年 5 月 10 日[!DNL Analytics]の Analytics メンテナンスリリースにおいて、日付が有効な分類と数値の分類の機能制限を開始しました。これらの分類タイプは、管理者および分類インポーターの各インターフェイスから削除されました。新しい日付が有効な分類や数値分類は追加できません。 既存の分類は、通常の分類ワークフローで引き続き管理（アップロード、削除）でき、レポートで使用できます。

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Classifications] を使用して、日付範囲をキャンペーンや他のコンバージョンに割り当てることができ、より正確 [!UICONTROL classifications]なキャンペーン測定が可能です。 値の日付範囲を指定した後、一致する値が日付範囲外に発生しても分類されません。 これは、キャンペーン自体に一致するすべてのヒットではなく、キャンペーンが実稼働していた正確な日付を利用するキャンペーン測定に役立ちます。 日付範囲を使用して値を正しく分類するには、次の条件を満たす必要があります。

* The [!UICONTROL classification] must be based on a conversion variable.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* 関連する日付範囲には、開始日と（オプションで）終了日が含まれている必要があります。

日付範囲に基づいてキャンペーンを分類する手順は、次のとおりです。

1. [!DNL Analytics] にログインし、管理者／分類に移動します。
1. Click the **[!UICONTROL Browser Export]** tab, ensure the settings to your date-enabled classification are correct, then click Export File.
1. このファイルを Microsoft Excel、またはその他の使い慣れているスプレッドシートエディターで開きます。
1. 列の 1 つが

   ^~period~ で終わり、日付範囲を入力する列であることを示します。
1. この列に、各値の日付範囲を

   `YYYY/MM/DD - YYYY/MM/DD`をインストールします。次の事項を確認してください。

   * ダッシュの両側にスペースを入れておきます。
   * 範囲を区切るにはハイフン(-)を使用し、enダッシュやemダッシュは使用しません。
   * 月または日が1桁の場合、先頭にゼロが付きます。
   * 日付範囲の開始日は必ず指定します。終了日はオプションです。

1. ファイルを保存し、管理者／分類／ファイルのインポートに移動して [!DNL Analytics] にアップロードします。

>[!NOTE]キー値に対して、複数の日付範囲は指定できません。

## 分類のトラブルシューティング

* [一般的な のアップロードの問題](https://helpx.adobe.com/jp/analytics/kb/common-saint-upload-issues.html)：不適切なファイル形式およびファイルの内容に起因する問題について説明したナレッジベース記事です。

