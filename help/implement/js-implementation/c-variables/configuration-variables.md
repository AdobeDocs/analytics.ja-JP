---
description: AppMeasurement. jsで設定された設定変数。
keywords: Analytics の導入
seo-description: Adobe Analytics用AppMeasurement. jsで設定された設定変数
seo-title: 設定変数
solution: Analytics
subtopic: 変数
title: 設定変数
topic: 開発者と導入
uuid: a19484b6- e350-4c12- b4d6- a31c79a42db0
translation-type: tm+mt
source-git-commit: 696e7ed6dc6648cf523bc81e6cd40c7a06115484

---


# 設定変数

設定変数は、データが取得され、レポートで処理される方法を制御します。一般的な設定変数は、主にメインのグローバルJavaScript AppMeasurement. jsに設定されます。これらの変数は、Analyticsページレベルのコードおよび必要に応じてリンク内で設定できます。

**[!UICONTROL 管理ツール]** / **[!UICONTROL コードマネージャー]**&#x200B;でコードを生成するときに、これらの変数の一部がコードにデフォルトで表示されるわけではありません。これらの設定変数の一部は、サイトの導入ニーズに当てはまらない可能性があります。

これらの設定変数を使用するうえでの目標の一部を次に示します。

* 複数のサイト／ドメインをトラッキングする。
* 購入時に任意の通貨を使用する。
* データに無関係な言語を取得する。
* リンクトラッキング（ダウンロードしたファイルの数、外部サイトへのリンク数）。
* 独自の用途でカスタムリンクをトラッキングする。

>[!NOTE]
>
>[!DNL AppMeasurement] track関数の最初の呼び出しの前に、すべての設定変数が設定されている必要 `t()`があります。If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

<!--
s_account.xml
-->

 変数は、データの保存とレポートをおこなうレポートスイートを決定します。

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. レポートスイート ID はアドビが決定します。

**パラメーター**

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 40 バイト | In the URL path | 該当なし | 該当なし |

各レポートスイート ID は、[!DNL Admin Console] で作成された値と一致している必要があります。各レポートスイート ID は 40 バイト以下にする必要がありますが、すべてのレポートスイートの合計（コンマ区切りリスト全体）には制限はありません。

レポートスイートは、レポーティングにおける最も基本的なレベルのセグメントです。レポートスイートは、契約で許される限り、いくらでも設定可能です。各レポートスイートは、アドビの収集サーバー上で確保されたデータ領域を参照します。レポートスイートは JavaScript コード内の`s_account` 変数によって指定されます。

[!DNL Analytics] 内では、レポートのヘッダー右上に現在のレポートスイートが表示されます。各レポートスイートは、レポートスイート ID と呼ばれる一意の識別子を持ちます。`s_account` 変数には、データを送信する1つまたは複数のレポートスイートIDが含まれています。このレポートスイート ID 値（[!DNL Analytics] ユーザーは見ることができない）は、使用の前にアドビから提供または承認される必要があります。すべてのレポートスイート ID には「わかりやすい名前」が関連付けられています。この名前は、[!DNL Admin Console] のレポートスイートセクションで変更することができます。

`s_account` この変数は通常、JavaScriptファイル（s_ code. js）内で宣言されます。You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. `s_account` JavaScriptファイルの読み込み時に値がない場合、データは送信されません [!DNL Analytics]。

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. パスの値が、送信先レポートスイートを決定する唯一の値です。次のボールドテキストは、デバッガーに表示される、データの送信先であるレポートスイートを示しています。詳しくは、 [DigitalPulse Debugger](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**構文と可能な値** {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

レポートスイート ID は、ASCII 文字の英数字文字列であり、40 バイト以下で指定する必要があります。使用できる英数字以外の文字はハイフンだけです。スペース、ピリオド、コンマ、その他の句読点は使用できません。"`s_account` 変数には、複数のレポートスイートを含めることができ、すべてのレポートスイートがページからデータを受け取ります。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of `s_account` must be provided or approved by Adobe.

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
* [!UICONTROL s. dynamicAccountSelection] がTrueに *設定されている場合、URL* は送信先レポートスイートを決定するために使用されます。送信先レポートスイートを確認する場合は、[!DNL DigitalPulse Debugger] を使用してください。

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

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* 各ページからデータを受信するレポートスイートを決定する場合は、必ず [!DNL DigitalPulse Debugger] を使用してください。

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

<!-- 
dynamicAccountList.xml
-->

[!DNL AppMeasurement]JavaScript 版 では、データ送信先のレポートスイートを動的に選択できます。 変数には、目的のレポートスイートを決定するために使用されるルールが含まれます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | "" |

この変数は、*`dynamicAccountSelection`**`dynamicAccountMatch`* と変数を使用します。The rules in *`dynamicAccountList`* are applied if *`dynamicAccountSelection`* is set to 'true,' and they apply to the section of the URL specified in *`dynamicAccountMatch`*.

If none of the rules in *`dynamicAccountList`* matches the URL of the page, the report suite identified in `s_account` is used. この変数で示されるルールは、左から右の順で適用されます。ページ URL が複数のルールと一致する場合、最も左にあるルールを使用してレポートスイートが決定されます。そのため、より一般的なルールをリストの右側に移動する必要があります。

In the following examples, the page URL is `www.mycompany.com/path1/?prod_id=12345` and `dynamicAccountSelection` is set to *true* and `s_account` is set to `mysuitecom.`

| DynamicAccountList の値 | DynamicAccountMatch の値 | データを受信するレポートスイート |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1、mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom、mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**構文と可能な値** {#section_7360E4354ED345E8BAAE210DBD58A7EC}

`dynamicAccountList` この変数は、name= valueのペア（ルール）のセミコロン区切りリストです。リストの各要素には以下の項目が含まれる必要があります。

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

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* ページ URL が複数のルールと一致する場合、最も左にあるルールが使用されます。
* 一致するルールがない場合、デフォルトのレポートスイートが使用されます。
* ページが他のユーザーのハードドライブに保存されているか、Web ベースの翻訳エンジンを介して翻訳されている場合（Google 翻訳後のページなど）は、動的アカウント選択はおそらく動作しません。より精度の高いトラッキングをおこなうには、`s_account` 変数をサーバーサイドで設定してください。
* `dynamicAccountSelection` ルールは、で指定したURLのセクションにのみ適用 `dynamicAccountMatch`されます。

* When using dynamic account selection, be sure to update *`dynamicAccountList`* every time you obtain a new domain.
* 送信先のレポートスイートを識別する際には、[!DNL DigitalPulse Debugger] を使用します。`dynamicAccountSelection` 変数は常に値を上書き `s_account`します。

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

<!-- 
dynamicAccountMatch.xml
-->

 変数は DOM オブジェクトを使用して、 のすべてのルールが適用される URL のセクションを取得します。

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' デフォルト値は [!DNL window.location.host] であるので、この変数は[!UICONTROL 動的アカウント選択]が動作するための必須の変数ではありません。For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

The rules found in `dynamicAccountList` are applied to the value of `dynamicAccountMatch`. If `dynamicAccountMatch` only contains [!DNL window.location.host] (default), the rules in `dynamicAccountList` apply only to the domain of the page.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | window.location.host |

**構文と可能な値** {#section_95CD81972C22419B80A921CA137D3841}

`dynamicAccountMatch` この変数は通常、JavaScript版AppMeasurementファイルを提供するアドビコンサルタントによって入力されます。ただし、以下に挙げる値はいつでも適用できます。

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

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* ページがハードドライブに保存されている場合、[!DNL window.location.host] は空になり、これらのページビュー数はデフォルトのレポートスイート（ `s_account`).

* ページが Google などの Web ベースの翻訳エンジンによって翻訳されている場合、[!UICONTROL 動的アカウント選択]は設計どおりに動作しません。より精度の高いトラッキングをおこなうには、[!UICONTROL s_account] 変数をサーバーサイドで設定してください。

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

<!-- 
dynamicVariablePrefix.xml
-->

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

<!-- 
charset.xml
-->

通常、JavaScriptファイルで設定されるcharSetプロパティは、Analyticsによって受信データをUTF-8に変換して、Analyticsで保存およびレポートするために使用されます。

>[!Ntoo:] charSetプロパティは、データをマルチバイトレポートスイートに送信するときに必要で、標準レポートスイートには絶対に使用しないでください。charSet プロパティを標準の ISO レポートスイートに設定すると、変数の切り捨てや予想外の文字変換が発生することがあります。

charSet プロパティの値は、たとえ構文がわずかに異なっていたとしても、META タグまたは http ヘッダーでの Web ページエンコーディングに一致する必要があります。META タグはエンコーディングにエイリアスを使用できますが、charSet の値は通称（または公式）のエンコーディング名を使用する必要があります。

次の表は、よく使用されるエンコーディングのいくつかをその通称とエイリアスで一覧表示したものです。

| 通称 | エイリアス |
|--- |--- |
| ISO-8859-1 | ISO_8859-1、CP819、latin1 |
| ISO-8859-2 | ISO_8859-2、latin2 |
| ISO-8859-5 | ISO_8859-5、cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

エンコーディングおよびエイリアスが多数存在するので、charSetの適切な値が上の表にない場合は、担当の導入コンサルタントまたはアドビカスタマーケアにお問い合わせください。

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

charSet パラメーターの空白でない値により、データは UTF-8 に変換されて保存されます。128～255 の範囲の文字は、適切な UTF-8 の 2 バイトシーケンスに変換されて保存されます。これらの文字は標準レポートスイートでは正しく表示されません。したがって、charSet プロパティは標準レポートスイートには絶対に使用しないでください。

同様に、charSet パラメーターの空白の値はデータ変換プロセスがスキップされ、128～255 の範囲の文字は 1 バイトとして保存されます。これらの文字の 1 バイトコードは有効な UTF-8 ではないので、これらの文字はマルチバイトレポートスイートでは正しく表示されません。したがって、charSet パラメーターは必ずマルチバイトレポートスイートで使用する必要があります。また、Web ページのエンコーディングに関しては適切な値を使用することが必要です。

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

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

<!-- 
currencycode.xml
-->

 変数は、売上高に適用される換算レートを決定します。

すべての売上は、選択した通貨で保存されます。その通貨が *`currencyCode`*&#x200B;が空 *`currencyCode`* の場合、コンバージョンは適用されません。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | cc | コンバージョン／購入／売上高 売上高または金額値を示すすべてのコンバージョンレポート | "USD" |

サイトで複数の通貨により購入できるようにしている場合は、*`currencyCode`* 変数を使用して、売上高を適切な通貨で保存する必要があります。For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. データ収集がそのデータを受け取るとすぐに、その時点の換算レートを使用して、この 40 ユーロを USD に換算します。

Populating the *`currencyCode`* variable on the HTML page instead of in the JavaScript file is recommend if you sell in multiple currencies. If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the *`currencyCode`* to equal the base currency of your report suite. その上で、すべての売上高を換算してから、[!DNL Analytics] に送信します。

通貨換算は、売上高と通貨イベントの両方に適用されます。通貨イベントとは、税金や送料など、売上高に類似した値を合計するために使用するイベントです。売上高および通貨イベントは、製品文字列内で指定します。products について詳しくは、 [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). 通貨の管理方法について詳しくは、[複数通貨のサポート](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/)を参照してください。

**構文と可能な値** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

[複数通貨のサポート](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/)で一覧表示されている通貨コードのみを使用できます。

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

* If you notice surprisingly large amounts of revenue in reports, ensure that the *`currencyCode`* variable and base currency of the report suite are set correctly.
* *`currencyCode`* 変数は永続的ではありません。つまり、売上高やその他の通貨関連指標と同じイメージリクエストで変数を渡す必要があります。
* 通貨イベントは、通貨以外の目的では使用しないでください。通貨ではない任意の値または動的な値をカウントする必要がある場合は、[!UICONTROL 数値]イベントタイプを使用してください。
* "*`currencyCode`* 変数が空の場合は、換算は適用されません。

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

<!-- 
cookiedomain.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. 例えば以下を使用して、ページの完全修飾名で Cookie を設定できます。

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

<!-- 
cookiedomainperiods.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. この変数は、一部のプラグインで、プラグインの cookie を設定するための適切なドメインを決定する際にも使用されます。

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain `www.mysite.com`, *`cookieDomainPeriods`* should be "2". For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain `www.mysite.co.jp`, the `s_cc` and `s_sq` cookies are created on the domain `co.jp`. `co.jp` は無効なドメインであるので、ほぼすべてのブラウザーでこれらの cookie が拒否されます。その結果、訪問者クリックマップ用のデータが消失し、[!UICONTROL 訪問者プロファイル]／[!UICONTROL 技術]／[!UICONTROL cookie] レポートに、ほぼ 100 ％の訪問者から cookie が拒否されたと示されます。

If *`cookieDomainPeriods`* が「3」で、ドメインにピリオドが 2 つだけ含まれている場合、JavaScript ファイルはサイトのサブドメインに対して cookie を設定します。For example, if setting *`cookieDomainPeriods`* to "3" on the domain `www2.mysite.com`, the `s_cc` and `s_sq` cookies are created on the domain `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". この変数定義によって、ルートドメイン [!DNL mysite.com] に対して cookie が正しく設定されます。Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

[s. fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274)も参照してください。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | CDP | 訪問者 ID の保存方法と処理方法を制御するため、複数のレポートに影響します。 | "2" |

>[!NOTE]
>
>一部のクラウドコンピューティングサービスは、cookieを書き込むことができないトップレベルドメインと見なされます。(For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) これらのサービスに実装すると、お客様の独自のドメインを設定していない場合（導入をテストする場合など）に、すべての Cookie をブロックしているユーザーを削除する Analytics のプライバシー設定による影響が生じることがあります。その場合は、システムによって Cookie が無効化されている、機能していないまたはアクセスできないと判断されたヒットは、すべてオプトアウトされるので、レポートからは除外されます。

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
* "*`cookieDomainPeriods`* 変数は、訪問者ID cookieを設定 *`trackingServer`* する前に、非推奨の実装で使用されていました。Though only present in outdated code, failure to correctly define *`cookieDomainPeriods`* in this circumstance puts your implementation at risk of data loss.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

<!-- 
fpCookieDomainPeriods.xml
-->

 変数は、導入でサードパーティ 2o7.net または omtrdc.net ドメインが使用されている場合でも、JavaScript（s_sq、s_cc、プラグイン）によって設定された本質的にファーストパーティの Cookie 用に使用されます。

*`fpCookieDomainPeriods`* 変数は動的に設定しないでください。If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* 値を継承 *`cookieDomainPeriods`* します。Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") ドメインが「www」で始まる場合のドメインのピリオド（.）の数を指します。For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

The [!DNL AppMeasurement] for JavaScript file uses the *`fpCookieDomainPeriods`* variable to determine the domain with which to set first-party cookies other than the [!UICONTROL visitor ID] (s_vi) cookie. この変数によって少なくとも 2 つの cookie が影響を受けます。s_sq および s_cc です（それぞれ訪問者クリックマップおよび cookie の確認に使用されます）。[!UICONTROL getValOnce] などのプラグインで使用される cookie も影響を受けます。

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

*`cookieDomainPeriods`* この変数は、以下のように文字列として想定されています。

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

<!-- 
cookielifetime.xml
-->

 変数は、JavaScript とデータ収集サーバーの両方で、Cookie の有効期限を決定するために使用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | cl | トラフィック／技術／cookie（訪問者関連のすべてのレポート） | "" |

If *`cookieLifetime`* が設定されている場合、JavaScript とデータ収集サーバーの両方について、その値が他のすべての cookie 有効期限よりも優先されますが、以下で説明するように 1 つだけ例外があります。*`cookieLifetime`* 変数には、次の3つの値のいずれかを指定できます。

* [!DNL Analytics] Cookie
* cookie
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

*`cookieLifetime`*[!DNL Analytics] の追跡に影響します。If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Use caution when setting *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

<!-- 
doPlugins.xml
-->

 変数は 関数への参照です。この変数を使用すると、JavaScript ファイル内の適切な場所で 関数を呼び出すことができます。

*`s_doPlugins`* 関数は、次のいずれかの処理を行うたびに呼び出されます。

* The *`t()`* function is called
* The *`tl()`* function is called
* 離脱リンクまたはダウンロードリンクがクリックされた
* 訪問者クリックマップによって追跡されているページ要素がクリックされた

"*`doPlugins`* 関数は、データの収集や変更のためのカスタマイズされたルーチンを実行するために使用します。If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the *`s_doPlugins`* function should be called s_mc_doPlugins.

**構文と可能な値** {#section_5CFB94598521455E80947964A306EA89}

The *`s_doPlugins`* function should not be in quotes, and *`doPlugins`* should always be assigned to the exact name of the *`s_doPlugins`* function (if that function is renamed).

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

* オブジェクト名を（s から s_mc などに）変更するのは、他の顧客とコンテンツを共有するか他の顧客のコンテンツを取り込む場合のみです。名前の変更&#x200B;*`s_doPlugins`* 関数を [!UICONTROL s_ mc_ doPlugins] に設定すると、別のクライアントのJavaScriptファイルが関数を *`doPlugins`* 上書きしないようになります。

* If you unexpectedly start pulling in content from another Adobe customer, and your *`s_doPlugins`* function is being overwritten, it is possible to simply rename the *`s_doPlugins`* function without changing the object name. 同じページ上の他の JavaScript ファイルとは異なるオブジェクト名を使用することが最善策ですが、これは必須ではありません。

## s. registerPreTrackCallbackおよびs. registerPostTrackCallback

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

<!-- 
trackDownloadLinks.xml
-->

サイト上のダウンロード可能ファイルへのリンクを追跡する場合は、 を「true」に設定します。

*`trackDownloadLinks`* が"true"の場合、どの *`linkDownloadFileTypes`* リンクがダウンロード可能ファイルであるかを判断するために使用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

"*`trackDownloadLinks`*&#x200B;サイトにダウンロード可能ファイルへのリンクがない場合、またはダウンロード可能ファイルのクリック数を追跡する必要がない場合は、trackDownloadLinks 変数を「false」に設定してください。If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. ダウンロードリンクで送信されるデータには、ダウンロードリンクの URL と、そのリンクの訪問者クリックマップ用のデータが含まれます。If *`trackDownloadLinks`* が"false"の場合、サイト上のダウンロード可能ファイルへのリンクの訪問者クリックマップデータが、レポートに表示される可能性が高くなります。

**構文と可能な値** {#section_828492CC2A144BC68D18C30CF397EEFC}

*`trackDownloadLinks`変数には、「true」または「false」を設定する必要があります。*

**例** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```js
s.trackDownloadLinks=true 
```

```js
s.trackDownloadLinks=false
```

**設定** {#section_9A5F69966BAF433A8DA2BCF655A652D1}

None

**注意事項、質問、ヒント** {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

<!-- 
trackExternalLinks.xml
-->

が"true"の場合、クリックされたリンクが離脱リンクであるかどうかを判断するために使用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

"*`trackExternalLinks`*&#x200B;サイトに離脱リンクがない場合、または離脱リンクのクリック数を追跡する必要がない場合は、trackExternalLinks 変数を「false」に設定してください。出口リンクは、訪問者がサイトから出て行くすべてのリンクです。If *`trackExternalLinks`* が"true"の場合、離脱リンクをクリックすると、トラッキングデータが直ちに送信されます。離脱リンクで送信されるデータには、リンクの URL、リンク名、そのリンクの訪問者クリックマップ用のデータが含まれます。If *`trackExternalLinks`* が"false"の場合、サイト上の離脱リンクの訪問者クリックマップデータは、レポートに表示される可能性が高くなります。

**構文と可能な値** {#section_267748949A7544658E1D838AAEF964B2}

*`trackExternalLinks`変数には、「true」または「false」を設定する必要があります。*

```js
s.trackExternalLinks=true|false
```

**例** {#section_EF18DB05884240F5B5062631E68E10A7}

```js
s.trackExternalLinks=true 
```

```js
s.trackExternalLinks=false
```

**設定** {#section_C8748CFE36324FAFB14C23E3E1FB5082}

None

**注意事項、質問、ヒント** {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

<!-- 
trackInlineStats.xml
-->

 変数は、ClickMap データを収集するかどうかを決定します。

*`trackInlineStats`* が"true"の場合、クリックされたページおよびリンクに関するデータはs_ sqというcookieに保存されます。If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | ClickMap | False |

**構文と可能な値** {#section_46B2C1DD0D104A01A9C239929420CD90}

```js
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

<!-- 
linkDownloadFileTypes.xml
-->

 変数は、コンマで区切られたファイル拡張子のリストです。

サイトにこれらの拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクがクリックされた場合にその URL が[!UICONTROL ファイルのダウンロード数]レポートに表示されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | トラフィック／サイトトラフィック／ファイルのダウンロード数 | "exe、zip、wav、mp3、mov、mpg、avi、wmv、doc、pdf、xls" |

"*`linkDownloadFileTypes`* 変数は、"True"に設定されている場合 *`trackDownloadLinks`* にのみ有効です。

リンク上でマウスを左クリックした場合にのみ、[!UICONTROL ファイルのダウンロード数]レポートでカウントされます。ページが読み込まれたときに自動的に開始されるファイルダウンロード、またはリダイレクトの後で実行されるファイルダウンロードはすべて、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。ファイルを右クリックし「対象をファイルに保存」オプションを選択した場合も、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。

"*`linkDownloadFileTypes`* 変数は、RSS フィードに対するクリック数を追跡するために使用することができます。If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the *`linkDownloadFileTypes`* list allows you to see how often each RSS link is clicked.

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
* 一般的なファイル拡張子のインクルード&#x200B;*`linkDownloadFileTypes`* に一般的なファイル拡張子を含めると、Adobe のサーバーに送信されるサーバーコール総数が大幅に増えることがあります。
* Links to server-side redirects or HTML pages that automatically begin downloading a file are not counted unless the file extension is in *`linkDownloadFileTypes`*.
* JavaScript（javascript:openLink( ) など）を使用するリンクは、ファイルのダウンロード数にはカウントされません。

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

<!-- 
linkInternalFilters.xml
-->

 変数は、サイトのどのリンクが離脱リンクであるかを判別するために使用されます。

これは、サイトの一部であるリンクを表すフィルターのコンマ区切りリストです。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク |  |

>[!NOTE]
>
>以前は、linkInternalFiltersをjavascript:に設定することを推奨していました。この方法では、タグが設定されている現在のドメインを含め、すべてのドメインが外部と認識されます。一部のドメインが内部と認識されるようにする場合は、以下の例のように、それらのドメインを追加できます。

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. 離脱リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが離脱リンクレポートに表示されるかどうかに影響しません。離脱リンクは、*`trackExternalLinks`* が `"true"` に設定されている場合に、スウォッチ選択の変更を発生させる秒単位の時間遅延です。（DTM による離脱リンクの処理方法について詳しくは、Dynamic Tag Management のドキュメントの[リンクトラッキング](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html)を参照してください）The filters in *`linkInternalFilters`* are not case-sensitive.

The list of filters in *`linkInternalFilters`* applies to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

貴社のサイトのすべてのドメイン（および貴社の JavaScript ファイルを使用しているすべてのパートナー）は、*`linkInternalFilters`* と呼ばれる iFrame を読み込みます。すべてのドメインをリストに含めていない場合、それらのドメイン上にあるリンクとそれらのドメインへのリンクはすべて、離脱リンクであると見なされ、送信されるサーバーコールの数が増加します。If you would like multiple domains or companies to use a single [!DNL AppMeasurement] for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. 直ちにメインドメインへリダイレクトされるバニティドメインがある場合、それらのバニティドメインをリストに含める必要はありません。

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

*`linkInternalFilters`* 変数は、ASCII文字のカンマ区切りリストです。スペースは使用できません。

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

<!-- 
linkLeaveQueryString.xml
-->

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
* `linkLeaveQueryString` この変数は、記録されたページのURL、訪問者クリックマップまたは [!UICONTROL パス] レポートには影響しません。

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

<!-- 
linkTrackVars.xml
-->

 変数は、カスタムリンク、離脱リンク、ダウンロードリンクで送信される変数のコンマ区切りのリストです。

*`linkTrackVars`* を"に設定すると、値を持つすべての変数がリンクデータと共に送信されます。To avoid inflation of instances or page views associated with other variables, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events."

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | いずれか | "なし" |

入力時&#x200B;*`linkTrackVars`*&#x200B;変数には"s."プレフィックスを使用しないでください。For example, instead of populating *`linkTrackVars`* with "s.prop1," you should populate it with "prop1." The following example illustrates how *`linkTrackVars`* should be used.

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

"*`linkTrackVars`* 変数には、送信先の変数のみを含めることができます。つまり [!DNL Analytics]、次のように指定します。 *`events`**`campaign`**`purchaseID`*、 *`products`*[!UICONTROL eVar1-75]、 [!UICONTROL prop1-75]、 [!UICONTROL hier1~5]*`channel`**`server`*、 *`state`**`zip`*&#x200B;および *`pageType`*.

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

* *`linkTrackVars`* が空白の場合、値を持つすべての変数がすべてのサーバーコールで追跡されます。
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* If *`linkTrackEvents`* is used, *`linkTrackVars`* must contain "events."

* 変数に「s.」または「s_objectname」のプレフィックスを使用しないでください。

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

<!-- 
linkTrackEvents.xml
-->

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

To avoid confusion and potential problems, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

*`linkTrackEvents`* 変数には、 [!UICONTROL カスタム]リンク、 [!UICONTROL ダウンロード]リンクおよび [!UICONTROL 離脱] リンクで送信されるイベントが含まれています。This variable is only considered if *`linkTrackVars`* contains "events."

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | コンバージョン | "なし" |

**構文と可能な値** {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

*`linkTrackEvents`* 変数はコンマ区切りのイベントリストです（スペースなし）。

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

* The JavaScript file only uses *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in *`linkTrackVars`* only when *`linkTrackEvents`* is defined.

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

<!-- 
linkExternalFilters.xml
-->

サイトに外部サイトへのリンクが多数含まれており、一部の離脱リンクは追跡する必要がない場合、 を使用すると、離脱リンクの特定のサブセットについてレポートすることができます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | パス／入口と出口／出口リンク | "" |

"*`linkExternalFilters`* 変数はオプションの変数で、リンクが離脱リンクかどうかを判断 *`linkInternalFilters`* するために使用されます。出口リンクは、訪問者がサイトから出て行くすべてのリンクとして定義されます。離脱リンクのターゲットウィンドウがポップアップであるか、既存のウィンドウであるかは、そのリンクが離脱リンクレポートに表示されるかどうかに影響しません。出口リンクは、*`trackExternalLinks`* は"true"に設定されています。The filters in *`linkExternalFilters`* and *`linkInternalFilters`* are case insensitive.

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

The filters list in *`linkExternalFilters`* and *`linkInternalFilters`* apply to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to 'true,' the filters apply to the entire URL (domain, path, and query string). これらのフィルターは、相対パスが href 値として使用されている場合でも、URL の絶対パスに常に適用されます。

ほとんどの企業では、*`linkInternalFilters`* では、不要な離脱リンクを十分に制御 *`linkExternalFilters`*&#x200B;できます。Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

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

*`linkExternalFilters`* 変数は、ASCII文字のカンマ区切りリストです。スペースは使用できません。

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

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Do not use this variable in place of *`linkInternalFilters`* to force internal links to become exit links.

* If *`linkExternalFilters`* should be applied to the query string of a link, make sure *`linkLeaveQueryString`* is set to 'true.' See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

<!-- 
s_usePlugins.xml
-->

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

[!UICONTROL usePlugins] が"true"の場合、 *`s_doPlugins`* 各イメージリクエストの前に関数が呼び出されます。

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

The [!UICONTROL usePlugins] variable should only be false (or not declared) if the *`s_doPlugins`* function is not declared in your JavaScript file.

**設定** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

None