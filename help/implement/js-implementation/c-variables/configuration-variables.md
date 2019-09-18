---
description: AppMeasurement.jsに設定される設定変数。
keywords: Analytics の実装
seo-description: AppMeasurement.jsで設定されたAdobe Analytics用の設定変数
seo-title: 設定変数
solution: Analytics
subtopic: 変数
title: 設定変数
topic: 開発者と実装
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 5b55b865629628da0ec42773355a1cf66ad7d9b7

---


# 設定変数

設定変数は、データが取得され、レポートで処理される方法を制御します。最も一般的な設定変数は、通常、メインのグローバルJavaScript appMeasurement.jsに設定されます。 これらの変数は、必要に応じて、Analyticsのページレベルコード内およびリンク内に設定できます。

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. これらの設定変数の一部は、サイトの導入ニーズに当てはまらない可能性があります。

これらの設定変数を使用するうえでの目標の一部を次に示します。

* 複数のサイト／ドメインをトラッキングする。
* 購入時に任意の通貨を使用する。
* データに無関係な言語を取得する。
* リンクトラッキング（ダウンロードしたファイルの数、外部サイトへのリンク数）。
* 独自の用途でカスタムリンクをトラッキングする。

>[!NOTE]
>
>[!DNL AppMeasurement] は、track関数の最初の呼び出しの前に、すべての設定変数が設定されている必要がありま `t()`す。 の呼び出しの後に設定変数が設定されている場合、予期しな `t()`い結果が発生する可能性があります。 To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

 変数は、データの保存とレポートをおこなうレポートスイートを決定します。

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. レポートスイート ID はアドビが決定します。

**パラメーター**

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 40 バイト | In the URL path | 該当なし | 該当なし |

各レポートスイート ID は、[!DNL Admin Console] で作成された値と一致している必要があります。各レポートスイート ID は 40 バイト以下にする必要がありますが、すべてのレポートスイートの合計（コンマ区切りリスト全体）には制限はありません。

レポートスイートは、レポーティングにおける最も基本的なレベルのセグメントです。レポートスイートは、契約で許される限り、いくらでも設定可能です。各レポートスイートは、アドビの収集サーバー上で確保されたデータ領域を参照します。レポートスイートは JavaScript コード内の`s_account` 変数によって指定されます。

[!DNL Analytics] 内では、レポートのヘッダー右上に現在のレポートスイートが表示されます。各レポートスイートは、レポートスイート ID と呼ばれる一意の識別子を持ちます。The `s_account` variable contains one or more report suite IDs to which data is sent. このレポートスイート ID 値（[!DNL Analytics] ユーザーは見ることができない）は、使用の前にアドビから提供または承認される必要があります。すべてのレポートスイート ID には「わかりやすい名前」が関連付けられています。この名前は、[!DNL Admin Console] のレポートスイートセクションで変更することができます。

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). 変数はHTMLページで宣言 `s_account` できます。これは、の値がページごとに変わる場合の一般 `s_account` 的な方法です。 Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. 場合によっては、の値も112.2o7.net `s_account` より前のドメインに表示されることがあります。 パスの値が、送信先レポートスイートを決定する唯一の値です。次のボールドテキストは、デバッガーに表示される、データの送信先であるレポートスイートを示しています。詳しくは、 [DigitalPulse Debugger](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**構文と可能な値** {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

レポートスイート ID は、ASCII 文字の英数字文字列であり、40 バイト以下で指定する必要があります。使用できる英数字以外の文字はハイフンだけです。スペース、ピリオド、コンマ、その他の句読点は使用できません。Folio Builder`s_account` 変数には、複数のレポートスイートを含めることができ、すべてのレポートスイートがページからデータを受け取ります。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

のすべての値は、ア `s_account` ドビが提供または承認する必要があります。

**例** {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

**Analytics** での変数の設定 {#section_7DFB2CCF02F045AFB1AD4F376638393B}

各レポートスイート ID に関連付けられているわかりやすい名前は、Adobe [!DNL Customer Care] によって変更できます。このわかりやすい名前は、[!DNL Analytics] の画面右上に表示されます。

**注意事項、質問、ヒント** {#section_BFFDA5C0AF31442494B0E02F0925CF93}

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. 送信先レポートスイートを確認する場合は、[!DNL DigitalPulse Debugger] を使用してください。

* 場合によっては、[!DNL VISTA] を使用して送信先レポートスイートを変更することができます。ファーストパーティ cookie を使用する場合、またはサイトに 20 を超えるアクティブなレポートスイートがある場合は、[!DNL VISTA] を使用して別のレポートスイートにデータを再ルーティングまたはコピーすることを推奨します。

* Always declare `s_account` inside the JS file or just before it is included.

## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

 変数を使用すると、各ページの URL に基づきレポートスイートを動的に選択できます。

>[!NOTE]
>
>`dynamicAccountSelection` はカスタムリンクトラッキングでは動作しません。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

**構文と可能な値** {#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

Only 'true' and 'false' are allowed as values of *`dynamicAccountSelection`*.

**例** {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

**設定** {#section_F052FA38144B4F84B015A263A8E711CF}

None

**注意事項、質問、ヒント** {#section_62F0B0895BC84A05840AEEED0643DE60}

* JavaScript版AppMeasurementでは、動的なアカウント選択はサポ [ートされていません](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)。
* 各ページからデータを受信するレポートスイートを決定する場合は、必ず [!DNL DigitalPulse Debugger] を使用してください。

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

[!DNL AppMeasurement]JavaScript 版 では、データ送信先のレポートスイートを動的に選択できます。 変数には、目的のレポートスイートを決定するために使用されるルールが含まれます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | "" |

この変数は、 と変 *`dynamicAccountSelection`* 数 *`dynamicAccountMatch`* を追加。 のルールは、 *`dynamicAccountList`* が「true」に設 *`dynamicAccountSelection`* 定され、で指定されたURLのセクションに適用される場合に適用されます *`dynamicAccountMatch`*。

のルールがページのURLに一致し *`dynamicAccountList`* ない場合は、で識別されたレポートスイートが使用 `s_account` されます。 この変数で示されるルールは、左から右の順で適用されます。ページ URL が複数のルールと一致する場合、最も左にあるルールを使用してレポートスイートが決定されます。そのため、より一般的なルールをリストの右側に移動する必要があります。

次の例では、ページURLは `www.mycompany.com/path1/?prod_id=12345` trueで `dynamicAccountSelection` 、 *は* true `s_account` に設定され、 `mysuitecom.`

| DynamicAccountList の値 | DynamicAccountMatch の値 | データを受信するレポートスイート |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1、mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom、mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**構文と可能な値** {#section_7360E4354ED345E8BAAE210DBD58A7EC}

The `dynamicAccountList` variable is a semicolon-separated list of name=value pairs (rules). リストの各要素には以下の項目が含まれる必要があります。

* 1 つ以上のレポートスイート ID（コンマ区切り）
* 等号
* 1 つ以上の URL フィルター（コンマ区切り）

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

文字列内では標準的な ASCII 文字のみを使用してください（空白は使用できません）。

**例** {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

**設定** {#section_9F99CD741BC7449B8CCC108094B2EB85}

None

**注意事項、質問、ヒント** {#section_3E10534FCC05457AB67147BB480C8BB3}

* JavaScript版AppMeasurementでは、動的なアカウント選択はサポ [ートされていません](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)。
* ページ URL が複数のルールと一致する場合、最も左にあるルールが使用されます。
* 一致するルールがない場合、デフォルトのレポートスイートが使用されます。
* ページが他のユーザーのハードドライブに保存されているか、Web ベースの翻訳エンジンを介して翻訳されている場合（Google 翻訳後のページなど）は、動的アカウント選択はおそらく動作しません。より精度の高いトラッキングをおこなうには、`s_account` 変数をサーバーサイドで設定してください。
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* 動的アカウント選択を使用する場合は、新しいドメインを取得す *`dynamicAccountList`* るたびに必ず更新するようにしてください。
* 送信先のレポートスイートを識別する際には、[!DNL DigitalPulse Debugger] を使用します。The `dynamicAccountSelection` variable always overrides the value of `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

 変数は DOM オブジェクトを使用して、 のすべてのルールが適用される URL のセクションを取得します。

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' デフォルト値は [!DNL window.location.host] であるので、この変数は[!UICONTROL 動的アカウント選択]が動作するための必須の変数ではありません。For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

に示すルールは、 `dynamicAccountList` の値に適用されます `dynamicAccountMatch`。 にのみ `dynamicAccountMatch` が含まれ [!DNL window.location.host] る場合（デフォルト）、のルールはペ `dynamicAccountList` ージのドメインにのみ適用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | window.location.host |

**構文と可能な値** {#section_95CD81972C22419B80A921CA137D3841}

The `dynamicAccountMatch` variable is usually populated by the Adobe consultant who provides the AppMeasurement for JavaScript file. ただし、以下に挙げる値はいつでも適用できます。

```js
s.dynamicAccountMatch=[DOM object]
```

| 説明 | 値 |
|---|---|
| ドメイン（デフォルト） | window.location.host |
| パス | window.location.pathname |
| クエリ文字列 | (window.location.search?window.location.search:"?") |
| ドメインとパス | window.location.host+window.location.pathname |
| パスとクエリ文字列 | window.location.pathname+(window.location.search?window.location.search:"?") |
| 完全修飾 URL | window.location.href |

**例** {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

**設定** {#**section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

None

**注意事項、質問、ヒント** {#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* JavaScript版AppMeasurementでは、動的なアカウント選択はサポ [ートされていません](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)。
* ページがハードドライブに保存されている場合、[!DNL window.location.host] は空になり、これらのページビュー数はデフォルトのレポートスイート（ `s_account`).

* ページが Google などの Web ベースの翻訳エンジンによって翻訳されている場合、[!UICONTROL 動的アカウント選択]は設計どおりに動作しません。より精度の高いトラッキングをおこなうには、[!UICONTROL s_account] 変数をサーバーサイドで設定してください。

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

 変数を使用すると、動的に設定する必要のある変数にフラグを付けることができます。

動的に設定できるものには、cookie、リクエストのヘッダーおよびイメージクエリ文字列パラメーターがあります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | D= | すべて | D= |

**構文と可能な値** {#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

または、動的変数用のカスタムフラグを使用します。

```js
s.dynamicVariablePrefix=".."
```

**例** {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

または、動的変数用のカスタムフラグを使用します。

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

**注意事項、質問、ヒント** {#section_6889908FBD78488D955F67DDB17617B1}

* 動的変数は、値を他の変数にコピーすることで、URL の全体的な長さを大幅に短縮するために使用できます。
* 動的変数は、データ収集では通常取得されないようなヘッダーおよび cookie からデータを収集するために使用できます。

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

通常JavaScriptファイルで設定されるcharSetプロパティは、Analyticsで、受信データをUTF-8に変換して、Analyticsでの保存とレポートに使用されます。

>[!N] 注意：charSetプロパティは、データをマルチバイトのレポートスイートに送信する場合に必要です。標準のレポートスイートでは絶対に使用しないでください。 charSet プロパティを標準の ISO レポートスイートに設定すると、変数の切り捨てや予想外の文字変換が発生することがあります。

charSet プロパティの値は、たとえ構文がわずかに異なっていたとしても、META タグまたは http ヘッダーでの Web ページエンコーディングに一致する必要があります。META タグはエンコーディングにエイリアスを使用できますが、charSet の値は通称（または公式）のエンコーディング名を使用する必要があります。

次の表は、よく使用されるエンコーディングのいくつかをその通称とエイリアスで一覧表示したものです。

| 通称 | エイリアス |
|--- |--- |
| ISO-8859-1 | ISO_8859-1、CP819、latin1 |
| ISO-8859-2 | ISO_8859-2、latin2 |
| ISO-8859-5 | ISO_8859-5、cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

エンコーディングやエイリアスが多数存在するので、charSetが上の表に表示されない場合は、導入コンサルタントまたはアドビカスタマーケアに問い合わせて、適切な値を確認してください。

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

charSet パラメーターの空白でない値により、データは UTF-8 に変換されて保存されます。128～255 の範囲の文字は、適切な UTF-8 の 2 バイトシーケンスに変換されて保存されます。これらの文字は標準レポートスイートでは正しく表示されません。したがって、charSet プロパティは標準レポートスイートには絶対に使用しないでください。

同様に、charSet パラメーターの空白の値はデータ変換プロセスがスキップされ、128～255 の範囲の文字は 1 バイトとして保存されます。これらの文字の 1 バイトコードは有効な UTF-8 ではないので、これらの文字はマルチバイトレポートスイートでは正しく表示されません。したがって、charSet パラメーターは必ずマルチバイトレポートスイートで使用する必要があります。また、Web ページのエンコーディングに関しては適切な値を使用することが必要です。

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. ただし、ページ上の変数にASCII以外の文字が含まれている場合は、その変数を入力す *`charSet`* る必要があります。

**パラメーター**

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | CE | 該当なし | "" |

**構文と可能な値** {#section_EBC2176067A04D9E814CF78A86DC80FA}

```js
s.charSet="character_set"
```

**例** {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

 変数は、売上高に適用される換算レートを決定します。

すべての売上は、選択した通貨で保存されます。その通貨が  *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | cc | コンバージョン／購入／売上高 売上高または金額値を示すすべてのコンバージョンレポート | "USD" |

サイトで複数の通貨により購入できるようにしている場合は、*`currencyCode`* 変数を使用して、売上高を適切な通貨で保存する必要があります。For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. データ収集がそのデータを受け取るとすぐに、その時点の換算レートを使用して、この 40 ユーロを USD に換算します。

Populating the *`currencyCode`* variable on the HTML page instead of in the JavaScript file is recommend if you sell in multiple currencies. アドビが使用するコンバージョン率ではなく、独自のコンバージョン率を使用する場合は、をレポートスイートのベ *`currencyCode`* ース通貨と同じに設定します。 その上で、すべての売上高を換算してから、[!DNL Analytics] に送信します。

通貨換算は、売上高と通貨イベントの両方に適用されます。通貨イベントとは、税金や送料など、売上高に類似した値を合計するために使用するイベントです。売上高および通貨イベントは、製品文字列内で指定します。products について詳しくは、 [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE).

**構文と可能な値** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

**例** {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

**設定** {#section_D05E29F545A04958B1C0A82248BCA1B0}

Adobe [!DNL Customer Care] が、レポートスイートのデフォルトの通貨設定を変更いたします。レポートスイートのベース通貨を変更した場合、システム内の既存の売上高は変換されません。新しい売上高の値はすべて、新しい通貨設定に従って変換されます。

**注意事項、質問、ヒント** {#section_08A80A87B54A4861905953A6FA61FF8F}

* レポートで驚くほど売上高が多い場合は、レポートスイートの変数とベ *`currencyCode`* ース通貨が正しく設定されていることを確認してください。
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* 通貨イベントは、通貨以外の目的では使用しないでください。通貨ではない任意の値または動的な値をカウントする必要がある場合は、[!UICONTROL 数値]イベントタイプを使用してください。
* When *`currencyCode`* 変数が空の場合は、換算は適用されません。

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. 例えば以下を使用して、ページの完全修飾名で Cookie を設定できます。

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. この変数は、一部のプラグインで、プラグインの cookie を設定するための適切なドメインを決定する際にも使用されます。

のデフォルト *`cookieDomainPeriods`* 値は「2」です。 This is the value that is used if *`cookieDomainPeriods`* is omitted. 例えば、ドメインを使用する場 `www.mysite.com`合は「2」 *`cookieDomainPeriods`* にする必要があります。 の場 `www.mysite.co.jp`合は、 *`cookieDomainPeriods`* 「3」に設定します。

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

例えば、ドメインで「2」 *`cookieDomainPeriods`* に設定した場合、ドメ `www.mysite.co.jp`インに `s_cc` 対してと `s_sq` cookieが作成されま `co.jp`す。 `co.jp` は無効なドメインであるので、ほぼすべてのブラウザーでこれらの cookie が拒否されます。その結果、訪問者クリックマップ用のデータが消失し、[!UICONTROL 訪問者プロファイル]／[!UICONTROL 技術]／[!UICONTROL cookie] レポートに、ほぼ 100 ％の訪問者から cookie が拒否されたと示されます。

if *`cookieDomainPeriods`* が「3」で、ドメインにピリオドが 2 つだけ含まれている場合、JavaScript ファイルはサイトのサブドメインに対して cookie を設定します。例えば、ドメインで「3」 *`cookieDomainPeriods`* に設定した場合、ドメ `www2.mysite.com`インに `s_cc` 対してと `s_sq` cookieが作成されま `www2.mysite.com`す。 When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. 例えば、「2」 `store.toys.mysite.com` に設定した *`cookieDomainPeriods`* ままの場合、 この変数定義によって、ルートドメイン [!DNL mysite.com] に対して cookie が正しく設定されます。Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

s.fpCookieDomainPeriods [も参照してください](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274)。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | CDP | 訪問者 ID の保存方法と処理方法を制御するため、複数のレポートに影響します。 | "2" |

>[!NOTE]
>
>一部のクラウドコンピューティングサービスはトップレベルドメインと見なされ、cookieの書き込みが許可されません。 (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) これらのサービスに実装すると、お客様の独自のドメインを設定していない場合（導入をテストする場合など）に、すべての Cookie をブロックしているユーザーを削除する Analytics のプライバシー設定による影響が生じることがあります。その場合は、システムによって Cookie が無効化されている、機能していないまたはアクセスできないと判断されたヒットは、すべてオプトアウトされるので、レポートからは除外されます。

**例** {#section_4218BE29FA5E49F58975A2094329B268}

変数を手動で設定します。

```js
s.cookieDomainPeriods = "3";
```

コア JavaScript ファイルで両方のタイプをホストしている場合に、変数を動的に設定するいくつかの例を示します。

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

**注意事項、質問、ヒント** {#section_F3BE3F039E5C4359B694DBB61369822C}

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. この設定により、訪問者がサブドメインを切り替えたときにデータが消失する可能性があります。
* Folio Builder 変数 *`cookieDomainPeriods`* は、訪問者ID cookieを設定する前に、非推奨の導入で *`trackingServer`* 使用されていました。 古いコードでのみ存在しますが、この状況で正しく定義できないと、実装 *`cookieDomainPeriods`* でデータが失われるリスクがあります。

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

 変数は、導入でサードパーティ 2o7.net または omtrdc.net ドメインが使用されている場合でも、JavaScript（s_sq、s_cc、プラグイン）によって設定された本質的にファーストパーティの Cookie 用に使用されます。

The *`fpCookieDomainPeriods`* variable should never be dynamically set . を使用する場 *`cookieDomainPeriods`*&#x200B;合は、の値も指定することをお勧め *`fpCookieDomainPeriods`* します。 *`fpCookieDomainPeriods`* は値を継承 *`cookieDomainPeriods`* します。 Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

「」とい *`fpCookieDomainPeriods`*&#x200B;う名前は、ピリオド(".")の数を表します。ドメインが「www」で始まる場合のドメインのピリオド（.）の数を指します。For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

for javaScriptフ [!DNL AppMeasurement] ァイルは、変数を使 *`fpCookieDomainPeriods`* 用して、訪問者ID  (s_vi) cookie以外のファーストパーティcookieを設定するドメインを決定します。 この変数によって少なくとも 2 つの cookie が影響を受けます。s_sq および s_cc です（それぞれ訪問者クリックマップおよび cookie の確認に使用されます）。[!UICONTROL getValOnce] などのプラグインで使用される cookie も影響を受けます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | cookieDomainPeriods |

**Cookie ドメイン変数の設定に関するサンプルコード** {#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

**構文と可能な値** {#section_87923F4C12E74AF99CC9AFC0FFD77D49}

The *`cookieDomainPeriods`* variable is expected to be a string, as shown below.

```js
s.fpCookieDomainPeriods="3"
```

**例** {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

**設定** {#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

None

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

 変数は、JavaScript とデータ収集サーバーの両方で、Cookie の有効期限を決定するために使用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | cl | トラフィック／技術／cookie（訪問者関連のすべてのレポート） | "" |

if *`cookieLifetime`* が設定されている場合、JavaScript とデータ収集サーバーの両方について、その値が他のすべての cookie 有効期限よりも優先されますが、以下で説明するように 1 つだけ例外があります。The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookie
* Cookie
* JavaScript 設定とプラグイン

**構文と可能な値** {#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

有効な値は以下のとおりです。

* ""
* "NONE"
* "SESSION"
* 有効期限が切れるまでの秒数を表す整数

**例** {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

**設定** {#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

None

**注意事項、質問、ヒント** {#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* はトラッキングに [!DNL Analytics] 影響します。 If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Use caution when setting *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

 変数は 関数への参照です。この変数を使用すると、JavaScript ファイル内の適切な場所で 関数を呼び出すことができます。

The *`s_doPlugins`* function is called each time any of the following occurs:

* 関数 *`t()`* が呼び出されます
* 関数 *`tl()`* が呼び出されます
* 離脱リンクまたはダウンロードリンクがクリックされた
* 訪問者クリックマップによって追跡されているページ要素がクリックされた

Folio Builder *`doPlugins`* 関数は、データの収集や変更のためのカスタマイズされたルーチンを実行するために使用します。If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. 例えば、オブジェクト名がs_mcの場合、関 *`s_doPlugins`* 数の名前はs_mc_doPluginsです。

**構文と可能な値** {#section_5CFB94598521455E80947964A306EA89}

関数 *`s_doPlugins`* は引用符で囲まないでください。関数名 *`doPlugins`* が変更された場合は、常に関数名に正確な名前を *`s_doPlugins`* 割り当てる必要があります。

```js
s.doPlugins=s_doPlugins;
```

**例** {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

**設定** {#section_641F0EC55E3349E5A3F8671446797074}

None

**注意事項、質問、ヒント** {#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* オブジェクト名を（s から s_mc などに）変更するのは、他の顧客とコンテンツを共有するか他の顧客のコンテンツを取り込む場合のみです。名前の変更 *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* 別のアドビの顧客から意図せずにコンテンツの取り込みを開始し、関数が上書きされる場合は、オブジェクト名を変更せずに、単に関数の *`s_doPlugins`**`s_doPlugins`* 名前を変更するだけで済みます。 同じページ上の他の JavaScript ファイルとは異なるオブジェクト名を使用することが最善策ですが、これは必須ではありません。

## s.registerPreTrackCallbackとs.registerPostTrackCallback

これらの関数は、コールバック（関数）およびそのパラメーターをパラメーターとして取ります。以下に例を示します。

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

コールバックは、`requestUrl` およびコールバックの登録時に渡されたパラメーターとともに呼び出されます。コールバックの登録に使用されたメソッドにより、この呼び出しはトラッキングコールの前または後に発生します。

これらのコールバックが呼び出される順序は保証されていません。トラッキングコール前フックで登録されるコールバックは、最終トラッキング URL の作成後に呼び出されます。トラッキングコール後フックのコールバックは、トラッキングコールの成功後に呼び出されます（トラッキングコールが失敗すると、コールバックは呼び出されません）。`registerPreTrackCallback` で登録されたコールバックは、トラッキングコールには影響しません。また、登録されたコールバックでいずれかのトラッキングメソッドを呼び出すことは、無限ループの原因となるおそれがあるため、推奨されていません。

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

サイト上のダウンロード可能ファイルへのリンクを追跡する場合は、 を「true」に設定します。

が「true」 *`trackDownloadLinks`* の場合は、どのリンクがダ *`linkDownloadFileTypes`* ウンロード可能ファイルかを判断するために使用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

Folio Builder *`trackDownloadLinks`*&#x200B;サイトにダウンロード可能ファイルへのリンクがない場合、またはダウンロード可能ファイルのクリック数を追跡する必要がない場合は、trackDownloadLinks 変数を「false」に設定してください。If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. ダウンロードリンクで送信されるデータには、ダウンロードリンクの URL と、そのリンクの訪問者クリックマップ用のデータが含まれます。if *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

**構文と可能な値** {#section_828492CC2A144BC68D18C30CF397EEFC}

*`trackDownloadLinks`変数には、「true」または「false」を設定する必要があります。*

**例** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

**設定** {#section_9A5F69966BAF433A8DA2BCF655A652D1}

None

**注意事項、質問、ヒント** {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

が「true」の場合、およびを使用して、クリックされたリンクが離脱リンクであるかどうかを判断します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

Folio Builder *`trackExternalLinks`*&#x200B;サイトに離脱リンクがない場合、または離脱リンクのクリック数を追跡する必要がない場合は、trackExternalLinks 変数を「false」に設定してください。出口リンクは、訪問者がサイトから出て行くすべてのリンクです。if *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. 離脱リンクで送信されるデータには、リンクの URL、リンク名、そのリンクの訪問者クリックマップ用のデータが含まれます。if *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

**構文と可能な値** {#section_267748949A7544658E1D838AAEF964B2}

*`trackExternalLinks`変数には、「true」または「false」を設定する必要があります。*

```
js
s.trackExternalLinks=true|false
```

**例** {#section_EF18DB05884240F5B5062631E68E10A7}

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

**設定** {#section_C8748CFE36324FAFB14C23E3E1FB5082}

None

**注意事項、質問、ヒント** {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

 変数は、ClickMap データを収集するかどうかを決定します。

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | ClickMap | False |

**構文と可能な値** {#section_46B2C1DD0D104A01A9C239929420CD90}

```
js
s.trackInlineStats=true|false
```

*`trackInlineStats`変数には、「true」または「false」を設定する必要があります。*

**例** {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

**設定** {#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

None

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

 変数は、コンマで区切られたファイル拡張子のリストです。

サイトにこれらの拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクがクリックされた場合にその URL が[!UICONTROL ファイルのダウンロード数]レポートに表示されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | トラフィック／サイトトラフィック／ファイルのダウンロード数 | "exe、zip、wav、mp3、mov、mpg、avi、wmv、doc、pdf、xls" |

Folio Builder 変 *`linkDownloadFileTypes`* 数は、が「True」に設定さ *`trackDownloadLinks`* れている場合にのみ関連します。

リンク上でマウスを左クリックした場合にのみ、[!UICONTROL ファイルのダウンロード数]レポートでカウントされます。ページが読み込まれたときに自動的に開始されるファイルダウンロード、またはリダイレクトの後で実行されるファイルダウンロードはすべて、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。ファイルを右クリックし「対象をファイルに保存」オプションを選択した場合も、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。

Folio Builder *`linkDownloadFileTypes`* 変数は、RSS フィードに対するクリック数を追跡するために使用することができます。.xmlまたは他の拡張子を持つRSSフィードへのリンクがある場合は、リストに「,xml」を追加すると、各RSSリンクがクリックされ *`linkDownloadFileTypes`* る頻度を確認できます。

**構文と可能な値** {#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

ファイル拡張子のみ含めます（スペースなし）。

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

リストにはどのようなファイル拡張子でも含めることができます。htm や aspx のような一般的なファイル拡張子は、*`linkDownloadFileTypes`* と呼ばれる iFrame を読み込みます。これらの拡張子を含めると、クリックごとに余分なイメージリクエストが送信されることになり、これはプライマリサーバーコールとして請求されます。

**例** {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

**設定** {#section_CE24D5852E4D441A958A4EDDB82382A7}

None

**注意事項、質問、ヒント** {#section_786CF22D5553429EB6524B13774793BC}

* ダウンロードファイルを左クリックした場合のみ、URL が[!UICONTROL ファイルのダウンロード数レポート]に表示されます。
* 共通のファイル拡張子を&#x200B;*`linkDownloadFileTypes`* に一般的なファイル拡張子を含めると、Adobe のサーバーに送信されるサーバーコール総数が大幅に増えることがあります。
* Links to server-side redirects or HTML pages that automatically begin downloading a file are not counted unless the file extension is in *`linkDownloadFileTypes`*.
* JavaScript（javascript:openLink( ) など）を使用するリンクは、ファイルのダウンロード数にはカウントされません。

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

 変数は、サイトのどのリンクが離脱リンクであるかを判別するために使用されます。

これは、サイトの一部であるリンクを表すフィルターのコンマ区切りリストです。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク |  |

>[!NOTE]
>
>以前は、linkInternalFiltersをjavascript：に設定することを推奨していました。 この方法では、タグが設定されている現在のドメインを含め、すべてのドメインが外部と認識されます。一部のドメインが内部と認識されるようにする場合は、以下の例のように、それらのドメインを追加できます。

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. 離脱リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが離脱リンクレポートに表示されるかどうかに影響しません。離脱リンクは、*`trackExternalLinks`* が `"true"` に設定されている場合に、スウォッチ選択の変更を発生させる秒単位の時間遅延です。（DTM による離脱リンクの処理方法について詳しくは、Dynamic Tag Management のドキュメントの[リンクトラッキング](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html)を参照してください）のフィルターでは、大 *`linkInternalFilters`* 文字と小文字が区別されません。

のフィルターのリストは、デ *`linkInternalFilters`* フォルトではリンクのドメインとパスに適用されます。 If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

貴社のサイトのすべてのドメイン（および貴社の JavaScript ファイルを使用しているすべてのパートナー）は、*`linkInternalFilters`* と呼ばれる iFrame を読み込みます。すべてのドメインをリストに含めていない場合、それらのドメイン上にあるリンクとそれらのドメインへのリンクはすべて、離脱リンクであると見なされ、送信されるサーバーコールの数が増加します。複数のドメインまたは会社で単一の [!DNL AppMeasurement] for javaScriptファイルを使用する場合は、JavaScriptファイルで指定された値を上書きして、ページに *`linkInternalFilters`* データを埋め込むことを検討してください。 直ちにメインドメインへリダイレクトされるバニティドメインがある場合、それらのバニティドメインをリストに含める必要はありません。

次の例では、この変数の使用方法を示します。In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

**構文と可能な値** {#section_810966F09912415B96EA9C2EDAE0CEA0}

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. スペースは使用できません。

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

**例** {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

**設定** {#section_546AC1FACB664ABFBCF312990097C987}

None

**注意事項、質問、ヒント** {#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* [!UICONTROL パス]／[!UICONTROL 入口と出口]／[!UICONTROL 離脱]リンクのレポートを定期的に調べて、レポートに含まれるエントリがすべて正しいことを確認してください。

* 定期的にパートナー契約を調べて、契約にリンクトラッキングに関する制限が含まれているかどうかを確認してください。例えば、パートナーのディスプレイ広告に表示されるリンクのトラッキングが禁止されている場合があります。次のようにパートナーのドメインを  *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeaveQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

デフォルトでは、クエリ文字列はすべての レポートから除外されます。

一部の離脱リンクやダウンロードリンクでは、次のサンプル URL に示すように、URL の重要な部分をクエリ文字列に含めることができます。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

ダウンロードファイル名をクエリ文字列内で定義することもあります。したがって、[!UICONTROL ファイルのダウンロード数]レポートをより正確にするためには、クエリ文字列が必要です。

The *`linkLeaveQueryString`* variable determines whether or not the query string should be included in the [!UICONTROL Exit Links] and [!UICONTROL File Download] reports.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | 離脱リンクファイルのダウンロード数 | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

**構文** {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

**例** {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

**可能な値** {#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

**設定** {#section_835FD74D3CA9425A9D091CACF88A6F1F}

この変数では設定は必要ありません。

**注意事項、質問、ヒント** {#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

 変数は、カスタムリンク、離脱リンク、ダウンロードリンクで送信される変数のコンマ区切りのリストです。

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. 他の変数に関連付けられたインスタンスやページビューの水増しを防ぐため、アドビでは、リンクトラッキ *`linkTrackVars`* ングに使 *`linkTrackEvents`* 用されるリンクの [!UICONTROL onClick] イベントにデータを埋め込むことをお勧めします。

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. を使 *`linkTrackEvents`* 用する場合は、 *`linkTrackVars`* 「events」を含める必要があります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | いずれか | "なし" |

埋め込み時 *`linkTrackVars`*, do not use the 's.' prefix for variables. 例えば、「s.prop1」 *`linkTrackVars`* を入力する代わりに、「prop1」を入力する必要があります。 次の例は、使用方法 *`linkTrackVars`* を示しています。

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

google.com へのリンクは離脱リンクであるので（現在の場所が Google である場合を除く）、event1 と eVar1 は離脱リンクデータと共に送信され、eVar1 に関連付けられているインスタンスの数および event1 の発生回数が増加します。In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

**構文と可能な値** {#section_DCC239F5CFE74959856764DAB1862BA7}

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. つまり、「s.eVar1」ではなく「eVar1」を使用します。

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

Folio Builder 変数に *`linkTrackVars`* は、送信先の変数のみを含めるこ [!DNL Analytics]とができます。 *`events`*,,,, *`campaign`* eVar1-75, *`purchaseID`* eVar1-75 *`products`*, prop1-75, [!UICONTROL prop1-prop1,]prop1, [!UICONTROL prop, prop,]prod, *`channel`**`server`**`state`**`zip`**`pageType`* prod.

**例** {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

**設定** {#section_E387604B8A434A7F89A82A886649A89D}

None

**注意事項、質問、ヒント** {#section_99E0783A608C4462945F35D21AB4AC2B}

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* を使 *`linkTrackEvents`* 用する場合は、 *`linkTrackVars`* 「events」を含める必要があります。

* 変数に「s.」または「s_objectname」のプレフィックスを使用しないでください。

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

[!DNL help.php] への最初のリンクでは、events 変数にはリンクがクリックされる前に設定された値が保持されています。これにより、event1 がカスタムリンクで送信されます。In the second example, the link to [!DNL test.php], event2 is not recorded because it is not listed in *`linkTrackEvents`*.

混乱や潜在的な問題を避けるため、アドビでは、リンクトラッキ *`linkTrackVars`* ングに使 *`linkTrackEvents`* 用するリ [!UICONTROL ンクのonClick] イベントにデータを埋め込むことをお勧めします。

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. この変数は、「events」が含まれ *`linkTrackVars`* る場合にのみ考慮されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | コンバージョン | "なし" |

**構文と可能な値** {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

The *`linkTrackEvents`* variable is a comma-separated list of events (no spaces).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

 *`linkTrackEvents`*. These events are listed in [Events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). イベント名の前または後ろにスペースがある場合、どのリンクイメージリクエストでもイベントは送信されません。

**例** {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

**設定** {#section_D938A47346D94A0C9E98FB327F2EF349}

None

**注意事項、質問、ヒント** {#section_DBB68BECC9D44380816113DB2566C38C}

* JavaScriptファイルは、「events」変数 *`linkTrackEvents`* が含ま *`linkTrackVars`* れる場合にのみを使用します。 「events」は、が定義されている場合にの *`linkTrackVars`* み含める必 *`linkTrackEvents`* 要があります。

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

サイトに外部サイトへのリンクが多数含まれており、一部の離脱リンクは追跡する必要がない場合、 を使用すると、離脱リンクの特定のサブセットについてレポートすることができます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク | "" |

Folio Builder 変数は、 *`linkExternalFilters`* リンクが離脱リンクであるかどうかを判断するた *`linkInternalFilters`* めにと組み合わせて使用されるオプションの変数です。 出口リンクは、訪問者がサイトから出て行くすべてのリンクとして定義されます。離脱リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが離脱リンクレポートに表示されるかどうかに影響しません。出口リンクは、 *`trackExternalLinks`* is set to 'true.' とのフィルターでは、大 *`linkExternalFilters`* 文字と *`linkInternalFilters`* 小文字が区別されません。

>[!NOTE]
>
>使用しない場合は、削除す *`linkExternalFilters`*&#x200B;るか、""に設定します。

デフォルトでは、のフィルタ *`linkExternalFilters`* ーリスト *`linkInternalFilters`* とは、リンクのドメインとパスに適用されます。 を「true」 *`linkLeaveQueryString`* に設定すると、フィルターはURL全体（ドメイン、パス、クエリ文字列）に適用されます。 これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

ほとんどの企業では、 *`linkInternalFilters`* gives them enough control over exit links that they don't need *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

次の例では、この変数の使用方法を示します。In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

**構文と可能な値** {#section_E35DAAAE8BDE44CEB8F6763EF1344693}

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. スペースは使用できません。

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

URL の任意の部分をコンマで区切って、*`linkExternalFilters`* から構成される明示的な画像セットを指定します。

**例** {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

**設定** {#section_2D0CA911855B4B3698145FC18D5021C3}

None

**注意事項、質問、ヒント** {#section_8B40E6F539E3473B934A8DB7C5086D73}

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. 内部リンクを強制的に離脱リンクにする場 *`linkInternalFilters`* 合は、の代わりにこの変数を使用しないでください。

* リン *`linkExternalFilters`* クのクエリ文字列に適用する必要がある場合は、が「true」に設 *`linkLeaveQueryString`* 定されていることを確認します。 See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

usePlugins [!UICONTROL が「true] 」の場合、各イメージリクエ *`s_doPlugins`* ストの前に関数が呼び出されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

**構文と可能な値** {#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

[!UICONTROL usePlugins] 変数には、「true」または「false」を設定する必要があります。

**例** {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

関数 [!UICONTROL がJavaScriptファイルで宣言されていない場合、] usePlugins変数はfalse(または宣言されて *`s_doPlugins`* いない)にする必要があります。

**設定** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

None