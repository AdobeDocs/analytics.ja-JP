---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics の実装
seo-description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
seo-title: ページ変数
solution: Analytics
subtopic: 変数
title: ページ変数
topic: 開発者と実装
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# ページ変数

ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

 変数は、ブラウザーウィンドウの高さを自動取得します。

<!-- 
browserheight.xml
-->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

**パラメーター**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> クエリパラメーター </th> 
   <th class="entry"> 値 </th> 
   <th class="entry"> 例 </th> 
   <th class="entry"> 影響を受けるレポート </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>正の整数 </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>トラフィック／技術／ブラウザーの高さ </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

 変数は、ブラウザーウィンドウの幅を自動取得します。

<!-- 

browserwidth.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

**パラメーター**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>クエリパラメーター</b> </p> </td> 
   <td> <p> <b>値</b> </p> </td> 
   <td> <p> <b>例</b> </p> </td> 
   <td> <p> <b>影響を受けるレポート</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>正の整数 </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>トラフィック／技術／ブラウザーの幅 </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

 変数は、訪問者をサイトに誘導するために使用されるマーケティングキャンペーンを識別します。通常、 の値はクエリ文字列パラメーターから取得します。

<!-- 

campaign.xml

 -->

**パラメーター**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 バイト </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>コンバージョン／キャンペーン／トラッキングコード </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

マーケティングキャンペーンのすべてのリンクに、一意のトラッキングコードを関連付ける必要があります。例えば、有料検索エンジンキーワードのトラッキングコードが 112233 であるとします。このトラッキングコード 112233 のキーワードをクリックした人が、対応する Web サイトに導かれた場合、*`campaign`* 変数にこのトラッキングコードが記録されます。

There are two main ways to populate the *`campaign`* variable:

* [!UICONTROL getQueryParam] プラグインを JavaScript ファイル内で使用して、URL からクエリ文字列パラメーターを取得します。[!UICONTROL getQueryParam] プラグインについて詳しくは、 [導入プラグイン](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Assign a value to the  variable in the HTML on the Web page.*`campaign`*

With either method of populating the  variable, the Back button traffic may inflate the actual number of click-throughs from a campaign element.*`campaign`*

例えば、ある訪問者が有料検索キーワードをクリックしてサイトに訪問したとします。この訪問者がランディングページに到達したとき、URL にはそのキーワードのトラッキングコードを識別するクエリ文字列パラメーターが含まれます。次に、この訪問者が別のページへのリンクをクリックした後、すぐに「戻る」ボタンをクリックしてランディングページに戻ったとします。この場合、この訪問者がランディングページに 2 回目に到達したとき、クエリ文字列パラメーターを含む URL によって、トラッキングコードが再び識別されます。この 2 回目のクリックスルーが登録されるので、クリックスルー数が誤って水増しされます。

このようなクリックスルー数の水増しを防ぐには、[!UICONTROL getValOnce] プラグインを使用して、各キャンペーンのクリックスルーをセッションあたり 1 回のみカウントするように設定することをお勧めします。[!UICONTROL getValOnce] プラグインについて詳しくは、 [導入プラグイン](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**構文と可能な値** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

The *`campaign`* variable has the same limitations as all other variables. 値の範囲を、標準的な ASCII 文字に制限することをお勧めします。

**大文字と小文字の区別** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

eVar では大文字と小文字が区別されませんが、表示上は、各単語の 1 文字目が大文字で示されます。例えば、eVar1 の最初のインスタンスを「Logged In」に設定し、以降のすべてのインスタンスを「logged in」として渡した場合、レポートには常に eVar の値として「Logged In」と表示されます。

**例** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**設定** {#section_4083F281968443169EAF8C0E8529D7BC}

campaign の各値はユーザーに対して引き続き有効となり、有効期限が切れるまで、そのユーザーのアクティビティおよび成功イベントのクレジットを受け取ります。campaign 変数の有効期限は Admin Console で変更できます。

**注意事項、質問、ヒント** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* クリックスルー数の水増しを防ぐには、[!UICONTROL getValOnce] プラグインを使用して、キャンペーンのクリックスルーがセッションあたり 1 回のみカウントされるようにします。[!UICONTROL getValOnce] プラグインについて詳しくは、 [導入プラグイン](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* マーケティングキャンペーンの追跡およびキーワードの購入について詳しくは、[キャンペーン](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html)を参照してください。
* キャンペーンの実際の値を確認するには、[!DNL DigitalPulse Debugger] を使用します（デバッガーで v0 を確認します）。デバッガーで v0 が表示されない場合は、そのキャンペーンデータは記録されていません。

## channel {#concept_C7770B8C15724A99B10F8F468AF82D0D}

 変数は、サイトのセクションを特定するためにもっともよく使用されます。

<!-- 

channel.xml

 -->

例えば、EC サイトなら、エレクトロニクス、玩具、アパレルなどのセクションが考えられます。メディアサイトなら、ニュース、スポーツ、ビジネスなどのセクションが考えられます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | ch | サイトコンテンツ／サイトセクション | "" |

すべてのページで channel 変数を設定することをお勧めします。また、*`channel`* 変数と[!UICONTROL ページ名]変数の間でクロス集計を有効にすることもできます。

When sections have one or more levels of subsections, you can show those sections in the *`channel`* variable or use separate variables to identify levels.

**構文と可能な値** {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

The *`channel`* variable has no extra limitations on its values.

**例** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**注意事項、質問、ヒント** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

If your site contains multiple levels, you can use the *`hierarchy`* or another variable to designate those levels. The *`channel`* value does not persist, but the success events fired on the same page are attributed to the *`channel`* value.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

 変数は、画面の各ピクセルで色を表示するためのビット数を示すために使用します。

<!-- 

colordepth.xml

 -->

例えば、「32」は、画面上の色が 32 ビットであることを示します。この変数の値は、ページコードの実行後、*`doPlugins`* の実行前に設定されます。

>[!NOTE]
>
>この変数は読み取り専用で、設定しないでください。

You may read these values and copy them into `props/eVars`, but you should never alter them. この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| c | 8、16 および 32 | 32 | トラフィック／技術／画面の色設定 |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

 変数は、Internet Explorer におけるブラウザーの接続設定（LAN 接続またはモデム接続）を示します。

<!-- 

conntype.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>この変数は読み取り専用で、設定しないでください。

You may read these values and copy them into `props/eVars`, but you should never alter them. この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| ct | lan または modem | lan | トラフィック／技術／接続のタイプ |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

 変数は、ファーストパーティセッション cookie が JavaScript によって設定できたかどうかを示します。

<!-- 

cookiesenabled.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>この変数は読み取り専用で、設定しないでください。

You may read these values and copy them into `props/eVars`, but you should never alter them. この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 |
|---|---|---|
| k | Y または N | Y |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

（廃止） 変数は、データの送信先のデータセンターを選択するために使用します。

<!-- 

dc.xml

 -->

>[!NOTE]
>
>dc 変数が廃止されました。すべての導入で、*`trackingServer`を s_code.js のコードマネージャーで生成される値に設定する必要があります。*

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | 112 |

この *`dc`* 変数では、[!UICONTROL ActionSource] に一致するようにデータセンターが識別されます。

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

[!UICONTROL eVar] 変数は、カスタムレポートを作成するために使用します。

<!-- 

eVarN.xml

 -->

eVar を訪問者に対して設定すると、その値が期限切れになるまで自動的に記憶されます。eVar 値がアクティブなときに訪問者に対して発生したすべての成功イベントは、その eVar 値にカウントされます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 255 バイト | V1-v75 ( or v100 or v250)[](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28) | カスタムコンバージョン | "" |

**Expiration** {#section_6DB5882B960D4660AE248B91B76883C4}

[!UICONTROL eVar] は、指定した期間が過ぎると有効期限切れになります。eVar の有効期限が切れた後は、成功イベントのクレジットを受け取らなくなります。eVar は、成功イベントの発生時に有効期限切れになるように設定することもできます。例えば、訪問の最後に有効期限切れになる内部プロモーションがある場合、その内部プロモーションは、アクティブ化された訪問中におこなわれた購入または登録に関するクレジットのみを受け取ります。

eVar を有効期限切れにする方法は以下の 2 つです。

* 指定した期間またはイベントの後に有効期限切れになるように eVar を設定できます。
* eVar の有効期限切れを強制的に適用することができます。これは、変数を再利用する場合に便利です。

If an eVar is used in May to reflect internal promotions and expires after 21 days, and in June it is used to capture internal search keywords, then on June 1, you should force the expiration of, or reset, the variable. これにより、内部プロモーションの値を 6 月のレポートから除外できます。

**大文字と小文字の区別** {#section_6E9145B7FCC2438E95BB35AAE3857412}

eVar では大文字と小文字が区別されませんが、表示上は、各単語の 1 文字目が大文字で示されます。例えば、eVar1 の最初のインスタンスを「Logged In」に設定し、以降のすべてのインスタンスを「logged in」として渡した場合、レポートには常に eVar の値として「Logged In」と表示されます。

**カウンター**{#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

eVar は、文字列値を保持するためによく使用されますが、カウンターとして動作するように設定されることもあります。eVar は、ユーザーがイベントの前に実行したアクション数をカウントする場合に、カウンターとして使用できます。例えば、購入前の内部検索数を取り込むために eVar を使用できます。訪問者が検索をおこなうたびに、eVar には「+1」した値が含まれます。訪問者が購入前に 4 回検索をおこなった場合、それぞれの合計数に関するインスタンス（1.00、2.00、3.00 および 4.00）を確認できます。ただし、4.00 のインスタンスのみが、購入イベント（注文指標および売上高指標）のクレジットを受け取ります。eVar カウンターの値には、正の数値のみを使用できます。

**下位関係** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

[!UICONTROL カスタム eVar] レポートでよくある要件は、ある[!UICONTROL カスタム eVar] レポートを別の eVar で分類することです。例えば、ある eVar に性別が含まれ、別の eVar に給料が含まれる場合に、「サイトの女性訪問者について、年収が $50,000 を超える女性によって生み出された売上高はどれほどか」という質問が考えられます。フルサブリレーションが有効な eVar を使用して、レポート内でこのような分類をおこなうことができます。例えば、性別を示す eVar でフルサブリレーションを有効にした場合、他のすべてのカスタム eVar レポートを性別ごとに分類し、性別は他のすべての eVar ごとに分類できます。2 つのレポート間の関係を参照する場合、フルサブリレーションを有効にする必要があるのは一方のみです。デフォルトでは、[!UICONTROL キャンペーン]、[!UICONTROL 製品]および[!UICONTROL カテゴリ]レポートではフルサブリレーションが有効です（任意の eVar をキャンペーンごとまたは製品ごとに分類できます）。

**構文と可能な値** {#section_BD46438B14F3488FB9AC42994C317B06}

While eVars may be renamed, they should always be referred to in the JavaScript file by eVarX, where X is a number between 1 and 75 ( [or 100, or 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

```js
s.eVarX="value"
```

カウンターとして使用しない eVar には、他のすべての変数と同じ制限があります。eVar が「カウンター」の場合は、「1」や「2.5」などの数値を受け取る必要があります。eVar カウンターで小数点以下が 3 桁以上ある場合は、2 桁に四捨五入されます。eVar カウンターには負の値は設定できません。

**例** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**設定** {#section_BD1FE63001C84D3DB69F3DEE243960B6}

eVars can be configured in Analytics &gt; Admin &gt; Report Suites &gt; Edit Settings &gt; Conversion &gt; Conversion Variables. すべての eVar は、[!UICONTROL 名前]、[!UICONTROL タイプ]、[!UICONTROL 配分]、[!UICONTROL 有効期限]設定または[!UICONTROL リセット]を使用して設定できます。それぞれの設定は個別に指定します。

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 設定 </th> 
   <th class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 名前 </td> 
   <td> <span class="keyword">Analytics</span> 内のレポート上で表示される eVar の名前を変更できます。 <p><span class="keyword"></span>指定した名前にかかわらず、JavaScript コード内では s.eVarX という名前で eVar を参照する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td> タイプ </td> 
   <td> eVar がテキスト文字列かカウンターかを設定します。 </td> 
  </tr> 
  <tr> 
   <td> 配分 </td> 
   <td> eVar のどの値が成功イベントのクレジットを受け取るかを設定します。 <p>「配分」が「最新 (最後)」に設定されている場合は、B がクレジットを受け取ります。 </p> <p>「配分」が「元の値 (最初)」に設定されている場合は、A がクレジットを受け取ります。 </p> <p>「配分」が「線形」に設定されている場合は、A と B の両方が購入値の半分のクレジットを受け取ります。 </p> </td> 
  </tr> 
  <tr> 
   <td> 有効期限 </td> 
   <td> eVar が購入などの特定のイベントの発生時に有効期限切れになるか、カスタムまたは事前定義された期間が過ぎた後に有効期限切れになるかを指定できます。 </td> 
  </tr> 
  <tr> 
   <td> リセット </td> 
   <td> eVar の「<span class="wintitle">リセット</span>」チェックボックスをオンにしてページの下の「<span class="wintitle">保存</span>」をクリックすると、その eVar のすべての値が即座に有効期限切れになります。この後は、その eVar の新しい値のみが成功イベントのクレジットを受け取ります。 </td> 
  </tr> 
 </tbody> 
</table>

**注意事項、質問、ヒント** {#section_DA6912C802E445F986C6DE4234C6C737}

* [!UICONTROL prop] 変数とは異なり、eVar 変数に値を区切ったリストを設定することはできません。eVar に値のリストを設定した場合（例：「one,two,three」）、このままの文字列がレポート内に表示されます。
* eVar カウンターには負の値は設定できません。

## イベント {#concept_FFD115543D54401B98FE683BD7D5B3FE}

 変数は、一般的な買い物かご成功イベントやカスタム成功イベントを記録するために使用します。

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 無制限 </td> 
   <td> events </td> 
   <td> <p>買い物かごイベント </p> <p>カスタムイベント </p> </td> 
   <td> 該当なし </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL イベント]は、サイト内のマイルストーンと見なされます。成功イベントは、会員登録やニュースレターの購読など、プロセスの最終的な完了ページで設定されることが最も一般的です。カスタムイベントは、以下の可能な値で定義されているリテラル値を使用して events 変数を設定することで定義されます。

デフォルトでは、成功イベントはカウンター&#x200B;**&#x200B;イベントとして設定されます。カウンターイベントは、成功イベントが設定された回数をカウントします（x+1）。また、イベントは&#x200B;*数値*&#x200B;イベントとしても設定できます。数値イベントを使用すると、数値の増分を指定できます（サイト内検索によって返される結果の数など、動的な値や任意の値をカウントする場合に必要となることがあります）。

通貨&#x200B;**&#x200B;イベントタイプは、数値イベントと同様に追加する数量を定義するために使用できますが、レポート内では通貨として表示され、s.*`currencyCode`* の値およびレポートスイートのデフォルトの通貨設定に基づいて通貨換算が実行されます。For additional information on using numeric and currency events, see [Products](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**変数の設定** {#section_9195286C34C54B02B2598E2B856492C3}

[!UICONTROL s.events] 変数は、すべての導入に対してデフォルトで有効化されます。事前設定済みの 7 つのコンバージョンイベントは、新しいレポートスイートで自動的に有効化されます。新しいカスタムイベント（event1 ～ [event100 または event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)）は、管理者レベルのユーザーが Admin Console を使用して有効にする必要があります。

**可能な値** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

以下に、events 変数で使用できる値の一覧を示します。

| イベント | 説明 | 入力されるレポート |
|---|---|---|
| prodView | 商品ビュー | 製品 |
| scOpen | 新しい買い物かごを開くまたは初期化 | 買い物かご |
| scAdd | 買い物かごへの品目の追加 | 買い物かごへの追加 |
| scRemove | 買い物かごからの品目の削除 | 買い物かごからの削除 |
| scView | 買い物かごの表示 | 買い物かご表示 |
| scCheckout | チェックアウトプロセスの開始 | チェックアウト |
| purchase | 購入（注文）の完了 | 購入回数 |
| event1 ～ event1000（ポイント製品の場合は event100） | カスタムイベント | カスタムイベント |

**構文と例** {#section_45A159DF00114066B8551DDEB15E084C}

カウンターイベントを設定するには、[!UICONTROL s.events] 変数に任意のイベントを配置します（複数のイベントを設定する場合はコンマ区切りのリストを使用します）。

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

H23 コード以降の場合、カウンターイベントには 1 より大きい整数を割り当てることができます。

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

整数値を割り当てたカウンターイベントを導入すると、そのイベントはイメージリクエスト内で複数回呼び出されたものとして扱われます。カウンターイベントでは小数は使用できません。小数の機能が必要な場合は、代わりに数値イベントを使用することをお勧めします。数値イベントと通貨イベントは、通常は [!UICONTROL s.products] 変数で数値（24.99 など）を受け取りますが、[!UICONTROL s.events] 変数に含める必要があります。こうすることで、特定の数値および通貨の値を個々の製品エントリに関連付けることができます。

**イベントのシリアル化** {#section_A89488EF4471405AAFC4D6DD05E77621}

デフォルトでは、サイトでイベントが設定されるたびにそのイベントがカウントされますが、重複判定による除外もできます。

See [Event Serialization](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705) for more information.

**構文** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**例** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```

## hierN {#concept_C4475D1584D544ACB4C0A573EB60FA08}

[!UICONTROL 階層]変数は、サイトの階層におけるページの位置を決定します。

<!-- 

hierN.xml

 -->

この変数は、サイト構造に 4 つ以上のレベルを持つサイトの場合に最も有効です。例えば、メディアサイトにスポーツ、ローカルスポーツ、野球、レッドソックスの 4 つのレベルがあるとします。誰かが野球ページを訪問すると、スポーツ、ローカルスポーツおよび野球のすべてのレベルにその訪問が反映されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 255 バイト | H1 ～ H5 | 階層 | "" |

使用できる[!UICONTROL 階層]変数は 5 つあります。これらの変数は、アドビカスタマーケアが有効化する必要があります。階層を有効化するときに、変数の区切り文字と、階層の最大レベル数を決定する必要があります。例えば、区切り文字がコンマの場合、スポーツ階層は以下のように表示されます。

```js
s.hier1="Sports,Local Sports,Baseball"
```

どのセクション名にも指定した区切り文字を使用しないようにしてください。例えば、あるセクション名が「Coach Griffin, Jim」の場合は、コンマ以外の区切り文字を選択する必要があります。階層のセクションごとの長さは 255 バイトに制限されます。また、変数の全長も 255 バイトに制限されます。階層の作成時に区切り文字を選択した後は簡単には変更できません。

既存の階層での区切り文字の変更については、アドビカスタマーケアにお問い合わせください。区切り文字は、|| や /|¥ のように複数の文字で構成することもできます（複数の文字で構成すると、階層のセクションで使用される可能性が低くなります）。

**構文と可能な値** {#section_0739948A68A2420DAB1CBEA3115A5A66}

区切り文字の前後に空白文字を入れないでください。以下の例の構文では、N は 1 から 5 までの数値になります。

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

階層のレベルを区切る以外の目的では、区切り文字を使用しないでください。区切り文字には任意の文字（または複数の文字）を使用できます。

**例** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**設定** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

None

**注意事項、質問、ヒント** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* 区切り文字は、階層の設定後は変更できないことがあります。階層の区切り文字を変更する必要がある場合は、アドビカスタマーケアにお問い合わせください。
* レベルの数は、階層の設定後は変更できないことがあります。

>[!NOTE]
>
>階層を変更すると、サービス料が発生する可能性があります。

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

 変数は、Internet Explorer において、現在のページがユーザーのホームページとして設定されているかを示します。

<!-- 

homepage.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| hp | Y または N | Y | トラフィック／技術／ホームページ |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

 変数は、Java がブラウザーで有効になっているかどうかを示します。

<!-- 

javaEnabled.xml

 -->

この変数は、ページコードが開始されてから doPlugins が実行されるまでの間に設定されます。

>[!NOTE]
>
>This variable should only be read and never set.

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| v | Y または N | Y | トラフィック／技術／Java |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

 変数は、ブラウザーでサポートされている JavaScript のバージョンを示します。

<!-- 

javascriptVersion.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>この変数は読み取り専用で、設定しないでください。

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| j | 1.0、1.1、1.2、... 1.7 | 1.7 | トラフィック／技術／JavaScript のバージョン |

JavaScript ファイルのバージョン H.10 以降では、バージョン 1.7（H.10 がリリースされた時点で最新のバージョン）までが正確に検出されます。JavaScript ファイルの前のバージョンでは、バージョン 1.3 までのみが検出されました。

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

The  variable is an optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link.

<!-- 

linkName.xml

 -->

The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 バイト </td> 
   <td> pev2 </td> 
   <td> <p>ファイルのダウンロード数 </p> <p>カスタムリンク </p> <p>離脱リンク </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL カスタムリンク]はトラッキングデータを送信するリンクを参照します。Folio Builder *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. If *`linkName`* is not populated, the URL of the link appears in the report.

**構文と可能な値** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

There are no limitations on *`linkName`* outside of the standard variable limitations.

**例** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**設定** {#section_F15FF429FC274F708D50DF79D4668EA3}

None

**注意事項、質問、ヒント** {#section_170A78452A7340B5B229713AC1FB71FA}

* The *`linkName`* variable is replaced by the third parameter in the *`tl()`* function.

* If the *`linkName`* variable and the third parameter in the *`tl()`* function are blank, the full URL of the link (with the exception of the query string) appears in the report (even if the link is relative).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

 変数はリンクトラッキングで使用されるオプションの変数で、リンク名や URL が表示されるレポート（カスタムリンク、ダウンロードリンクまたは離脱リンク）を決定します。

<!-- 

linkType.xml

 -->

The *`linkType`* variable is not normally needed because the second parameter in the *`tl()`* function replaces it.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 1 文字 </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>ファイルのダウンロード数 </p> <p>カスタムリンク </p> <p>離脱リンク </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

カスタムリンクはデータを Analytics に送信します。The *`linkType`* variable (or the second parameter in the *`tl()`* function) is used to identify the report in which the link name or URL appears ( [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report).

離脱リンクとダウンロードリンクの場合、クリ *`linkType`* ックされたリンクが離脱リンクかダウンロードリンクかに応じて、変数が自動的に設定されます。 A custom link may be configured to send data to any of the three reports with this variable or with the second parameter in the *`tl()`* function. 「 *`linkType`* o」、「e」または「d」を設定すると、またはリンクURLがカスタムリンク、 *`linkName`* Custom Links 、 [!UICONTROL File Downloads]exit reportにそれぞれ送信され  ます。

**構文と可能な値** {#section_18DB3A8083FB4F75B970055ED336DA4E}

The *`linkType`* variable syntax depends on whether you use XML or a query string.

XML を使用する場合は、変数には 1 つの文字（o、e または d）のみが含まれます。

```js
s.tl(this,’o’,’Link Name’);
```

If you are using the query-string `pe`, you need to use `lnk_d`, `lnk_e`, or `lnk_o`.

**例** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**設定** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

None

**注意事項、質問、ヒント** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* を指 *`linkType`* 定しない場合、カスタムリンク('o')が想定されます。

## リスト prop {#concept_83ED74232225431F83A796E22FFC75B4}

リスト prop は、変数に渡され、レポートの個別行項目としてレポートされる値の区切りリストです。リスト prop は、一般的に、チェックボックスやラジオボタンのリスト項目などの、ユーザーが複数選択できる項目を計測するために導入されます。リスト prop は、複数のイメージリクエストを送信せずに 1 つの変数で複数の値を定義する場合に役立ちます。

<!-- 

list_props.xml

 -->

**注意点**

* リスト prop はトラフィック変数（[prop](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254)）のオプションです。
* パスおよびクロス集計は、リスト prop では有効にできません。
* リスト prop レポートを含む、ほとんどすべてのレポートに訪問数および個別訪問者数を追加できます。
* リスト prop では分類がサポートされています。
* カスタムトラフィック変数はどれもリスト props として使用できます（例外： [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328)、 [channel](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D)、 [server](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2))。

* 同じイメージリクエストに重複した値が定義される場合、インスタンスの重複は除外されません。

prop は、管理ツール／レポートスイート／トラフィック変数ページでリストのサポートを有効にして、区切り文字を選択することで、リスト prop に変更できます。一般的な区切り文字はコロン、セミコロン、コンマ、またはパイプです。技術的には、ASCII 文字の最初の 127 文字のいずれもでも可能です。

**実装例** {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

リスト prop の有効化をリクエストする場合、使用する区切りを指定します。希望する *`s.prop`* が有効にされると、次の例に示されるように、変数に複数の値を設定できます。

パイプで区切られたリスト prop で、2 つの値を受け渡す：

```js
s.prop1="Banner ad impression|Sidebar impression"
```

コンマで区切られたリスト prop で、複数の値を受け渡す：

```js
s.prop2="cerulean,vermilion,saffron"
```

リスト prop では 1 つの値を受け渡すことも可能：

```js
s.prop3="Single value"
```

区切りはいつでも変更できます。ただし、実装では新しい区切りと一致する必要があります。正しい区切りを使わなかった場合、リスト prop の値は連結された単一の行項目としてレポートで扱われます。

リスト prop はトラフィック変数でもあるので、トラフィック変数の制限を受けることにもなります。リスト prop のデータは 100 バイトに制限され、大文字と小文字の区別に関する設定の影響を受けます。

## リスト変数 {#concept_AC42F2D69B674C02A484137CE5B4E687}

リスト Var とも呼ばれます。リスト Prop の機能と同様、リスト Var は同じイメージリクエスト内で複数の値を同時にセットできます。eVar とも似ており、定義されたイメージリクエストの完了後も保持されます。これらの変数を使うと、単一のページにある複数のエレメントの原因と効果を確認できます。製品リスト、ウィッシュリスト、検索絞り込みのリスト、表示広告などの計測に便利です。

<!-- 

listN.xml

 -->

**注意点**

* リスト Var は、訪問者のブラウザーにある VisitorID cookie を参照することによって特定の値をサーバー側で記憶します。
* 最大値 250 の制限は、訪問者ごとに 1 回格納されます。訪問者 1 人あたり 250 個という制限を超過した場合、最新の 250 個が使用されます。これらの値の有効期限は、変数の設定済み有効期限に基づきます。
* 区切られたそれぞれの値には最大 255 文字の値を含めることができます（全角文字の場合はそれ以下）。これは、各エレメントの最大長です。
* 変数内の文字数には制限はありません。唯一の例外として、古いバージョンの Internet Explorer ブラウザー内では、すべての URL リクエストが 2083 文字以内に制限されます。
* レポートスイートごとに合計 3 つのリスト Var が使用可能です。
* リスト Var を使用するには H23 コード以降が必要です。
* リスト Var は分類できます。
* 同じイメージリクエストで重複する値が定義されると、リスト Var はこれらの値のすべてのインスタンスで重複を除外します。
* セグメント化できる最も詳細な単位は、1 ヒット（またはページビュー）レベルです。同じイメージリクエストで 3 つの値を持つリスト Var がある場合、1 つの値に一致するセグメントルールによって、3 つの値すべてがレポートに取り込まれます。反対に、定義されている除外ルールが 1 つの値に一致する場合、3 つすべての値が除外されます。

**Configuration** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

Adobe ClientCare の関与なく Admin Console の設定にアクセスし、更新できます。

1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**
1. レポートスイートを選択します。
1. Click  **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

* **名前**：区切られたそれぞれの値には最大 255 文字の値を含めることができます（全角文字の場合はそれより少ない）。これは、各エレメントの最大長です。
* **値の区切り**：リスト Var 内で値を区切る文字。最も一般的なものとして、コンマ、コロン、パイプなどがあります。

   >[!NOTE]
   >
   >Multi-byte characters are not supported as delimiters in List Vars. 区切り文字は 1 バイト文字にする必要があります。

* **有効期限**：eVar の有効期限と同様に、リスト Var とコンバージョンイベントとの間で関連付けが生じるまでの経過時間の上限を指定します。

   * **ページビューまたは訪問レベル**：該当するページビューまたは訪問を超えた成功イベントはリスト Var 内の値にリンクされません。
   * **日、週、月などに基づいた期間**：指定した期間を超えた成功イベントはリスト Var 内の値にリンクされません。カスタム設定した日数を定義することもできます。
   * **特定のコンバージョンイベント**：指定した特定のイベント以降に発生した成功イベントはリスト Var 内の値にリンクされません。
   * **なし**：リスト Var と成功イベントとの間の経過時間に上限はありません。

* **配分**：各値に成功イベントのクレジットをどのように配分するかを決定します。

   * **フル**：変数の有効期限が切れる前に定義されたすべての変数の値に成功イベントのフルクレジットが付与されます。
   * **線形**：変数の有効期限が切れる前に定義されたすべての変数の値に、コンバージョンイベントの配分（等分）されたクレジットが付与されます。
   * 変数の値は、上書きされるのではなく、成功イベントのクレジットを受け取る値に追加されます。

* **最大値**：リスト変数で保持するアクティブ値の数を指定します。例えば 3 に設定すると、保存される値は直近の 3 個に限られ、それよりも前に取り込まれた値はすべて破棄されます。最大値を使用して値の数を制限しているときに、同じリスト Var に対して同じヒットで複数の値が送信される場合、そのすべての値のタイムスタンプが同じになり、どの値が保存されるのかについては保証されません。

   最大値 250 の制限は、訪問者ごとに 1 回格納されます。訪問者 1 人あたり 250 個という制限を超過した場合、最新の 250 個が使用されます。これらの値の有効期限は、変数の設定済み有効期限に基づきます。

   最大値の設定は、属性を特定の数の値に限定する場合に便利です。例えば、訪問した最初のページでリスト Var を「A,B,C」に設定し、次のページで「X,Y,Z」に設定した場合、属性は割り当てに基づいてこの 6 個の値に配布されます。属性を「X,Y,Z」のみに制限したい場合は、最大値を 3 に設定します。

To set up or edit List Vars, go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

**実装例** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

次のいずれの例も、値の区切りとしてコンマを使用しています。

**リスト Var 内で 1 つの値を定義する：**

```js
s.list1="Cat";
```

**複数の値を渡す：**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**売上高をリスト Var に関連付ける：**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

結果では、売上高がそれぞれ $50 となる 3 つの行項目が表示されます。（Top Banner Ad、Side Bar Ad、および Internal Campaign 1）このレポートの合計では重複を削除するため、合計でも $50 となります。

**売上高を訪問時に複数回設定されたリスト Var に関連付ける：**

**配分**：フル

**有効期限**：訪問

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ページ </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events および s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ページ 1 </td> 
   <td colname="col2"> <code> s.list1=”value1,value2,value3”; </code> </td> 
   <td colname="col3"> （未設定） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページ 2 </td> 
   <td colname="col2"> <code> s.list1=”value4,value5,value6”; </code> </td> 
   <td colname="col3"> <p> <code> s.events=”purchase”; </code> </p> <p> <code> s.products=”;product;1;200” </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**結果**：訪問中にリスト var1 に設定されたすべての値（value1、value2、value3、value4、value5、value6）が購入のフルクレジットを受けとります。

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

s.maxDelay 変数は Genesis DFA 統合で主に使用され、DFA ホストと通信する際のタイムアウト時間を指定します。 変数に設定された指定の時間内にアドビが DFA のサーバーから応答を受信しない場合、接続が切断されますが、データは通常どおりに処理されます。各ページで DFA の応答時間を使用する場合は、この変数を導入してください。この値を試行し、最適なタイムアウト時間を判断することをお勧めします。

<!-- 

maxDelay.xml

 -->

**導入例**

```
s.maxDelay="750";
```

**プロパティ**

* この値はオプションのイベント指標で、サイトに導入された JavaScript を通して指定されます。
* DFA ホストが定められた時間内に応答しない場合、タイムアウトするように指定されているイベントが実行されます（Genesis 統合ウィザードにより割り当て）。
* この変数には数値のみを含めることができます。
* 指定された時間はミリ秒単位で計測されます。
* 待機時間を増加させるとより多くの DFA データが収集されますが、Analytics のヒットデータを失うリスクも高くなります。

   Losing Analytics hit data would occur when the user navigates away from the page during the *`s.maxDelay`* period.

* 待機時間を減少させると Analytics のヒットデータを失うリスクは低くなりますが、ヒットデータと一緒に送信される DFA データの量は少なくなります。

   DFA統合データの損失は、期間がDFAホストの応 *`s.maxDelay`* 答に十分な時間を満たさない場合に発生します。

>[!NOTE]
>
>アドビはDFAの応答時間を制御できません。 最大遅延期間を妥当な時間枠に増やした後でも整合性の問題が見られる場合は、貴社の DFA アカウント管理者にお問い合わせください。

## mediaLength {#concept_F52B1670122C4461824223E525307060}

この変数は、再生中のメディアの合計長さを指定します。

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> pev3 リクエスト全体に対しては最大サイズはありません。サイズはブラウザーにおける URL の長さの限度に制限されます。 </td> 
   <td> pev3 </td> 
   <td> ビデオ滞在時間、 <p>閲覧ビデオセグメント </p> </td> 
   <td> なし </td> 
  </tr> 
 </tbody> 
</table>

**構文と可能な値** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

** autoTrackメソッド：**

[!UICONTROL s.Media.autoTrack] を使用する場合、[!UICONTROL mediaLength] 変数を明示的に導入する必要はありません。この変数は、JavaScript 版 AppMeasurement コードによって自動的に判別されます。

**手動トラッキングメソッド：**

構文：

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能な値：

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**例** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**注意事項、質問、ヒント** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* [!UICONTROL s.Media.autoTrack] を true に設定してもプレイヤーを追跡できない場合にのみ、メディアトラッキングメソッドを呼び出す必要があります。
* [!UICONTROL autoTrack] を使用したトラッキングでない場合は、長さを秒数で設定するようにしてください。

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

この変数はビデオまたはメディアの名前を指定します。

<!-- 

mediaName.xml

 -->

この変数は、[!UICONTROL Data Insertion API] と[!UICONTROL フル処理のデータソース]を介してのみ使用できます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 64 KB | pev3 | ビデオ、次のビデオフロー、前のビデオフロー、閲覧ビデオセグメント、ビデオ滞在時間 | なし |

**構文と可能な値** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**autoTrack メソッド：**

[!UICONTROL s.Media.autoTrack] を使用する場合、*`mediaName`* 変数を明示的に導入する必要はありません。この変数は、JavaScript 版 AppMeasurement コードによって自動的に判別されます。

**手動トラッキングメソッド：**

構文：

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

可能な値：

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**例** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**注意事項、質問、ヒント** {#section_941A445BB52E4063B0F6920E61BB90DE}

* [!UICONTROL s.Media.autoTrack] を true に設定してもプレイヤーを追跡できない場合にのみ、メディアトラッキングメソッドを呼び出す必要があります。
* この変数は、VARCHAR(100) とは対照的に、mySQL TEXT 変数として格納されます。

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

この変数はビデオまたはメディアを使用するプレイヤーを指定します。

<!-- 

mediaPlayer.xml

 -->

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | pev3 | ビデオプレイヤー | なし |

**構文と可能な値** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**autoTrack メソッド：**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**手動トラッキングメソッド：**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能な値：

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**例** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**注意事項、質問、ヒント** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

s.Media.autoTrack を true に設定してもプレイヤーを追跡できない場合にのみ、メディアトラッキングメソッドを呼び出す必要があります。

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

この変数は、使用されるビデオまたはメディアアセットのセグメントを指定します。

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 バイト </td> 
   <td> pev3 </td> 
   <td> ビデオ滞在時間 <p>閲覧ビデオセグメント </p> </td> 
   <td> なし </td> 
  </tr> 
 </tbody> 
</table>

**構文と可能な値** {#section_9A63266633C4427CB4A6549E4D887B85}

**autoTrack メソッド：**

[!UICONTROL s.Media.autoTrack] を使用する場合、*`mediaName`* 変数を明示的に導入する必要はありません。この変数は、JavaScript 版 AppMeasurement コードによって自動的に判別されます。

**手動トラッキングメソッド：**

構文：

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

可能な値：

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**例** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**注意事項、質問、ヒント** {#section_1BCEB037AB724B6EBE87420BD3604B88}

[!UICONTROL s.Media.autoTrack] を true に設定してもプレイヤーを追跡できない場合にのみ、メディアトラッキングメソッドを呼び出す必要があります。

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

 変数は、どのイベントがメディアヒットと共に送信されるかを示します。

<!-- 

media_trackEvents.xml

 -->

この変数は、JavaScript と [!UICONTROL ActionSource] でのみ適用できます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | s.Media.trackEvents="None" |

**構文と可能な値** {#section_66A978EF56914BEAAE73359A268A1B4A}

event1、purchase などのイベント名。

**例** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents=”event1,purchase”
```

**注意事項、質問、ヒント** {#section_030B11C64EE84D46A85CA550DB732D28}

この変数を入力するときは、必ず [!UICONTROL trackVars] に "events" と入力してください。

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

 変数は、どの変数がメディアヒットと共に送信されるかを示します。

<!-- 

media_trackVars.xml

 -->

この変数は、JavaScript と [!UICONTROL ActionSource] でのみ適用できます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | s.Media.trackVars="None" |

**構文と可能な値** {#section_7374684A7EB34AE685E8C40A66CFD289}

変数名( [!UICONTROL propN]、 *`eVarN`*、 *`events`**`channel`*&#x200B;など)。

**例** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars=”prop2,events,eVar3”
```

**注意事項、質問、ヒント** {#section_615AE1B696124B00B78F651B03813EAB}

* [!UICONTROL trackVars] で eVar3 を指定した場合でも、この変数はメディアヒットと共に送信されます。

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

 変数は、訪問者の識別に使用される cookie と加入者 ID の順序を制御します。

<!-- 

mobile.xml

 -->

See [Mobile network protocols](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | イメージ URL のパス内の /5/ または /1/ | 該当なし | なし |

**構文と可能な値** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**注意事項、質問、ヒント** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

訪問者間の識別を使用して、JavaScript cookie実装で変数を使用する場合に訪問者トラフィックのスパ *`s.mobile`* イクが発生する可能性を軽減します。

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

 変数には、サイトの各ページの名前が含まれます。

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 バイト </td> 
   <td> pageName </td> 
   <td> <p>ページ </p> <p>パス </p> </td> 
   <td> ページ URL </td> 
  </tr> 
 </tbody> 
</table>

Folio Builder *`pageName`* 変数には、ビジネスユーザーにとってわかりやすい値を入力する必要があります。ほとんどの場合、値 *`pageName`* はURLやファイルのパスではありません。 Common *`pageName`* values include names such as "Home Page," "Checkout," "Purchase Thank you," or "Registration."

改行文字、em ダッシュ（長いダッシュ）、en ダッシュ（短いダッシュ）または HTML 文字が、ページ名やその他の変数に使用されないように注意してください。改行文字を送信するブラウザーもありますが、送信しないブラウザーもあります。これにより、Analytics のデータが、外見上は同じ 2 つのページ名に分割される場合があります。多くの Office アプリケーションや電子メールクライアントでは、入力時にハイフンが自動的に en ダッシュまたは em ダッシュに変換されます。en ダッシュおよび em ダッシュは Analytics 変数では無効な文字なので（128 以上のコードの ASCII 文字）、Analytics では無効な文字を含むページ名が記録されず、代わりに URL が表示されます（日本語を有効化したレポートスイートを除く）。

If *`pageName`* is left blank, the URL is used to represent the page name. Leaving *`pageName`* blank is often problematic because the URL may not always be the same for a page `www.mysite.com` and `mysite.com` are the same page with different URLs).

**構文と可能な値** {#section_7A61EE70F1A84D26B414404998C84BA8}

The *`pageName`* variable should contain a useful identifier for business users of Analytics.

```js
s.pageName="page_name"
```

There are no limitations on *`pageName`* outside of the standard variable limitations.

**例** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**設定** {#section_58CBC68C805344A999EB47455FEBA8D5}

管理者は、[!UICONTROL ページに名前を付ける]ツールを使用して Analytics でのページの表示名を変更することができますが、このツールによって問題が発生する可能性があり、レポートに悪影響が出る場合があります。ページに名前を付けるツールを使用するには、アドビ[!UICONTROL カスタマーケア]にお問い合わせください。

**注意事項、質問、ヒント** {#section_BB41DC9682C34385B9CAA80D5257C113}

に不正な文字が含ま *`pageName`* れていないことを確認してください。

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

 変数は、404（ページが見つかりません）エラーページを指定する目的でのみ使用します。

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 バイト </td> 
   <td> pageType </td> 
   <td> パス／ページ／ページが <p>見つかりません </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Folio Builder *`pageType`* 変数は、404 エラーページが表示されたときにのみ固定文字列をセットします。これにより、リンク切れをすばやく見つけることができます。次に示すように、エ *`pageType`* ラーページで変数を設定します。

404 エラーページではページ名変数を使用しないでください。Folio Builder *`pageType`* 変数は、404 エラーページにのみ使用されます。

ほとんどの場合、404 エラーページはハードコードされた静的なページです。このような場合、.JS ファイルへの参照が適切な絶対または相対パス／ディレクトリに設定されていることが重要です。

**構文と可能な値** {#section_C1C59968226446559B05F6EE7374D525}

次に示すように、の *`pageType`* 唯一の許可値は「errorPage」です。

```js
s.pageType="errorPage"
```

**例** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**設定** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

None

**注意事項、質問、ヒント** {#section_943681AB01FE47BEAC72E93CB60C53C8}

To capture other server-side errors (such as 500 errors), use a prop to capture the error message and put "`500 Error: <URL>`" where `<URL>` is the URL requested, in the *`pageName`* variable. この一連の操作に従うことで、[!UICONTROL パス]レポートを使用して、500 エラーの発生原因となったパスを確認することができます。prop によって、サーバーからどのエラーメッセージが提示されたかがわかります。

## pageURL {#concept_A15F710CD0174297A2286BF3E7452113}

 変数は、ページの実際の URL よりも優先されます。

<!-- 

pageURL.xml

 -->

まれに、ページの URL が Analytics でレポートしたい URL ではないことがあります。

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 無制限* </td> 
   <td> <p>g </p> </td> 
   <td> トラフィック／セグメント化／最頻訪問ページ、パス </td> 
   <td> ページ URL </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Although Adobe allows *`pageURL`* values up to 64k, some browsers impose a size limit on the URL of image requests. To prevent truncation of other data, page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter.

**構文と可能な値** {#section_22AF3BF7C2F743549967B0C760A095C0}

The *`pageURL`* variable must be a valid URL, with a valid protocol. ドメインは、レポートに入力される前に強制的に小文字表示になり、クエリ文字列は、Analytics の設定に応じて削除される場合があります。

```js
s.pageURL="proto://domain/path?query_string"
```

URL と互換性のある文字のみページ URL として許可されます。

>[!NOTE]
>
>カスタム目的で変数を使用する前に、アドビのコンサルタントまたはカスタマーケアにお問い合わせ *`pageURL`* いただくことを強くお勧めします。

**例** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**設定** {#section_A8F77DAD88164528ACC5C16C066B47DF}

None

## plugins {#concept_B570F04FEDA34EB7A9826687FE633953}

 変数は、Netscape および Mozilla ベースのブラウザーで、ブラウザーにインストールされているプラグインを列挙します。

<!-- 

plugins.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| p | 認識されるプラグイン | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Windows Media Player Plug-in Dynamic Link Library;Microsoft® DRM; | トラフィック／技術／プラグイン |

## products {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

 変数は、製品と製品カテゴリ、および購入数量と購入価格を追跡するために使用します。一般に、products は、買い物かごイベントや イベントと共に設定されます。

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. この更新により、*`prodView`イベントが増加することがあります。**`prodViews`* は、次の場合にのみ増加します。
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
   >
   >
1. *`products`変数が空ではない。*
>
>
考えられる副作用として、*`prodView`* イベントによってトリガーされるマーチャンダイジング eVar は、空の *`product`* と関連付けられることがありますが、これは、*`product list`に無効な product のみが含まれる（product がリストされていないセミコロンなど）場合にのみ発生します。*

The *`products`* variable tracks how users interact with products on your site. 例えば、products 変数を使用して、製品の表示、買い物かごへの追加、チェックアウトおよび購入の各回数を追跡できます。サイトでのマーチャンダイジングカテゴリの相対的効果を追跡することもできます。products 変数を使用する場合は、次のようなシナリオが一般的です。

The *`products`* 変数は、必ず成功イベントと組み合わせて設定する必要があります。

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>「 <span class="wintitle"> products 」 </span>文字列の最大サイズは64kです。 </p> </td> 
   <td> products </td> 
   <td> 製品 <p>カテゴリ（オプション） </p> <p>売上高（オプション） </p> <p>購入点数（オプション） </p> <p>カスタムイベント（オプション） </p> <p>eVar（オプション） </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**構文** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| フィールド | 定義 |
|---|---|
| カテゴリ | 関連付けられている製品カテゴリを含みます。バージョン 15 では、products を複数のカテゴリに関連付けることができるようになり、バージョン 14 に存在した制限を修正しています。これまでに製品カテゴリを記録していなかった場合、これからは、バージョン 15 のレポートスイート用に、このフィールドに値を設定してください。 |
| Product | （必須）製品を追跡するために使用される識別子。この識別子は、[!UICONTROL 製品]レポートのデータを設定するために使用されます。チェックアウトプロセス全体で同じ識別子を必ず使用してください。 |
| Quantity | 購入した数量。このフィールドは、記録される[!UICONTROL 購入]イベントと共に設定する必要があります。 |
| Price | 個々の価格ではなく、購入総量の連結コスト（数量 x 単価）を表します。このフィールドは、[!UICONTROL 購入]イベントと共に設定する必要があります。 |
| イベント | 指定された製品に関連付けられる通貨イベント。詳しくは、[製品固有の通貨イベント](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C)および[注文全体にわたる通貨イベント](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0)を参照してください。 |
| eVars | 特定の製品に関連付けられるマーチャンダイジング eVar 値[マーチャンダイジング変数](/help/components/c-variables/c-merch-variables/var-merchandising.md)を参照してください。 |

The values included in the *`products`* 変数に含まれる値は、記録しているイベントの種類に基づきます。Category を省略するときは、プレースホルダーとしてカテゴリと製品の区切り文字（;）が必要です。含めるパラメーターを区別する必要がある場合に限り、他の区切り文字が必要です。

**購入以外のイベントによる products 変数の設定** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

The *`products`* variable must be set in conjunction with a success event.

**購入イベントによる products 変数の設定** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

The *`purchase`* event should be set on the final confirmation ("Thank You!") 設定する必要があります。製品名、カテゴリ、数量および価格はすべて  *`products`* variable. Although the *`purchaseID`* variable is not required, it is strongly recommended in order to prevent duplicate orders.

**製品固有／通貨イベント** {#section_F814DF053C0D463A97DA039E6323720C}

通貨イベントがイベント変数ではなく変数内の値を受け *`products`* 取った場合、その値にのみ適用されます。 これは、製品固有の割引額や送料などの値を追跡するのに役立ちます。例えば、製品送料を追跡するように event1 を設定した場合、送料が「4.50」の製品は、次のように表示されます。

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

この例では、値 4.50 は、製品「Running Shoes」に直接関連付けられます。event1 を製品レポートに追加すると、「4.50」は、行項目「Running Shoes」に表示されます。Price と同様、この値は表示される数量の合計を反映する必要があります。2 つの製品があり、それぞれの送料が 4.50 の場合、event1 は「9.00」になる必要があります。

**注文全体にわたる通貨イベント** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

通貨イベントが変数ではなくイベントリストの値を受け取った場合、そ *`products`* の通貨イベントは変数内のすべての製品に適用さ *`products`* れます。 これは、個別の製品に対してセットする価格に影響を与えることなく、または製品リスト内の製品価格を別に追跡することによって、注文全体にわたる割引額や送料などの値を追跡するのに役立ちます。

例えば、event10 に注文全体にわたる割引額を設定した場合、10 ％割引のある購入は以下のようになります。

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

通貨イベントのレポートでのレポートの合計は、重複を排除したイベントの合計（この例では、レポート期間中の割引の総量）を表し、各製品に対するイベントの値の合計ではありません。例えば、「Running Shoes」と「Running Socks」の両方に「9.95」と表示され、合計も「9.95」になります。

>[!NOTE]
>
>同じ数値/通貨イベントの値が変数と変数で指定さ *`products`* れている場合は、そ *`events`* の値が使用 *`events`* されます。

**注意事項、質問、ヒント** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* The *`products`* variable should always be set in conjunction with a [!UICONTROL success] event (events). [!UICONTROL 成功]イベントが指定されない場合、デフォルトのイベントは [!UICONTROL prodView] になります。

* 製品名およびカテゴリ名を products 変数に入力する前に、これらの名前からコンマとセミコロンをすべて取り除きます。
* HTML 文字（登録商標記号、商標など）をすべて取り除きます。
* 価格から通貨記号を取り除きます。

**例** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category;ABC123” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category2;ABC123,;ABC456” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category3;ABC123;1;10” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category;ABC123;1;10,;ABC456;2;19.98” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2,event3” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2,event3=9.95” </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

プロパティ（[!UICONTROL prop]）変数は、[!UICONTROL トラフィックモジュール]内でカスタムレポートを作成するために使用します。

<!-- 

propN.xml

 -->

prop 変数は、パスレポートやクロス集計レポートで、（ページビューが送信された回数をカウントするために）カウンターとして使用することができます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | c1 ～ c75 | カスタムトラフィック | "" |

**構文と可能な値** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

[!UICONTROL プロパティ]変数には、標準的な変数の制限以外の制限はありません。

**例** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**設定** {#section_25FDEB6ECA8242A2A44EE540C083078A}

prop 変数用の[!UICONTROL 訪問]指標、[!UICONTROL 訪問者]指標および[!UICONTROL パス]指標の表示については、アドビ[!UICONTROL カスタマーケア]にお問い合わせください。

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

 は、レポートで注文が複数回カウントされるのを防ぐために使用します。

<!-- 

purchaseID.xml

 -->

Whenever the [!UICONTROL purchase] event is used on your site, you should use the *`purchaseID`* variable.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 20 バイト | purchaseID | コンバージョン／購入／売上高、コンバージョン | "" |

訪問者がサイトで品目を購入したとき、*`purchaseID`* が、[!UICONTROL 購入]イベントが発生した「ご購入ありがとうございました」ページに対して設定されます。If the *`purchaseID`* is populated, the products on the "Thank You" page are counted only once per *`purchaseID`*. サイトへの多くの訪問者が、それぞれの目的で「ご購入ありがとうございました」ページ（「確認ページ」）を保存するので、1 回だけカウントされることは非常に重要です。Folio Builder *`purchaseID`* は、ページが表示されるたびに購入がカウントされるのを防ぎます。

購入データが2回カウントされるのを防ぐだけでなく、を使用すると、す *`purchaseID`*&#x200B;べてのコンバージョンデータがレポートで二重にカウントされるのを防ぎます。

**構文と可能な値** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

The *`purchaseID`* must be 20 characters or fewer, and be standard ASCII.

**例** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**設定** {#section_1808631C96674380BF9C4A6D9A2C568E}

None

**注意事項、質問、ヒント** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

The *`purchaseID`* variable allows all conversion variables on the page to be counted only once in reports.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

 変数は、失われたリファラー情報を復元するために使用できます。

<!-- 

referrer.xml

 -->

サーバーサイドと JavaScript のリダイレクトは、訪問者を正しい場所にルーティングするためによく使用されます。ただし、ブラウザーがリダイレクトされると、元の参照 URL は失われます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 255 バイト | R | トラフィック／検索方法、コンバージョン／検索方法 | document.referrer |

多くの企業では、Web サイト内の多数の場所でリダイレクトを使用します。例えば、訪問者を検索エンジンの有料検索結果からのリダイレクト経由で送信します。ブラウザーがリダイレクトされると、リファラーは多くの場合失われます。The 変数は、 *`referrer`* リダイレクト後に最初のページの元 *`referrer`* の値を復元するために使用できます。 The *`referrer`* may be populated server-side, or via JavaScript from the query string.

Analytics でリファラーを記録するには、リファラーが「整形式」であることが必要です。つまり、標準の URL 形式に従っており、プロトコルと適切な場所を含んでいる必要があります。

**構文と可能な値** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

 *`referrer`*. 文字列が URL エンコード（スペースなし）されていることを確認します。

**例** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**設定** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

None

**注意事項、質問、ヒント** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

The *`referrer`* must look like a standard URL and include a protocol.

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

 変数は、Web ページを表示する訪問者の画面の解像度を示します。

<!-- 

resolution.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>この変数は読み取り専用で、設定しないでください。

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| s | W x H | 1680 x 1050 | トラフィック／技術／画面の解像度 |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

The  variable is a global variable that should be set in the [!UICONTROL onClick] event of a link.

<!-- 

s_objectID.xml

 -->

By creating a unique object ID for a link or link location on a page, you can either improve visitor activity tracking or use [!UICONTROL Activity Map] to report on a link type or location, rather than the link URL.

>[!NOTE]
>
>A trailing semicolon (;) is required when using s_objectID with [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | OID | [!UICONTROL Activity Map]、 [!UICONTROL ClickMap] | クリックされたリンクの絶対 URL |

s_objectID を使用する一般的な理由には、 *`s_objectID`*:

* 1 日のうちに頻繁に変化する訪問者のアクティビティを集計するため。
* To separate link activity that [!UICONTROL Activity Map] combines.
* To improve the accuracy of [!UICONTROL Activity Map] data reporting.

**非常に動的なリンクに対するクリック数を集計する** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

サイトが非常に動的で、一部のページ上のリンクが1日を通して変化する場合は、を使用して *`s_objectID`* ページ上のリンクの場所を特定できます。 を「 *`s_objectID`**`s_objectID`* top left 1」または「top left 2」（例えば、ページの左上にある最初のリンクを表す）に設定した場合、その場所に表示される（または同じ値に設定された）すべてのリンクが、訪問者クリックマップと共にレポートされます。 If you don't use *`s_objectID`*, you see the number of times that a specific link was clicked, but you lose insight into how all the other links in that location were used by visitors to your site.

**合算されるクリック数を分解する** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

訪問者が *`pageName`**`s_objectID`* 閲覧している特定のページではなく、訪問者が閲覧しているセクションまたはテンプレートを表示するためにサイトの変数を使用する場合は、そのページテンプレートの複数のバージョンに表示されるリンクを分割するのに使用できます。 例えば、1 つのテンプレートページでサイト上のすべての製品に対応している場合、すべてのページに、そのテンプレートからホームページおよび検索ボックスへ移動するリンクが表示される可能性があります。これらのリンクが、テンプレートごとではなく、個々の製品ごとにどのように使用されているかを確認する場合は、*`s_objectID`* に、「prod 123789 home page」や「prod 123789 search」などの製品固有の値を入力できます。Once completed, [!UICONTROL Activity Map] reports on those links at an individual product basis.

**Activity Map[!UICONTROL の精度の向上]**{#section_08B3406821294DCCABEEB99C90CF5C52}

Internet Explorer、Firefox、Netscape、Opera、Safari 以外のブラウザーはレポートされないことがあります。このような状況が発生する割合が小さくても、クリック数やその他の指標に影響することがあります。Use *`s_objectID`* within links to uniquely identify the addresses the browser reporting issue. s_objectID を使用するためにリンクを更新する方法の例を *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**構文と可能な値** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID にはテキストの識別子を含めることができます。

```js
s_objectID="unique_id" 
```

～に制限はない。*`s_objectID`* には、標準的な変数の制限以外の制限はありません。

**例** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**設定** {#section_95396657D55B41ECB66B83D0534EA827}

None

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

 変数は、Web ページのドメイン（ユーザーがアクセスするドメインを表示）またはページを提供するサーバー（ロードバランシングのクイック参照用）を示すために使用されます。

<!-- 

server.xml

 -->

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | server | サーバー | "" |

サイトに同じコンテンツを提供する複数のドメインが存在する場合は、*`server`* 変数を使用して、訪問者が使用しているドメインを追跡できます。次の JavaScript は、ページのドメインを server 変数に入力します。

```js
s.server=window.location.hostname
```

server 変数を使用してロードバランシングの結果確認手段を提供する場合は、サーバーの名前または番号を server 変数に設定します。次の例を参照してください。

```js
s.server="server 14"
```

[!UICONTROL 最頻訪問サーバー]レポートはロードバランシングのクイック参照として使用できますが、サーバー負荷の正確な測定値を示すものではありません。例えば、「戻る」ボタントラフィックによってサーバー負荷は高くなりませんが、レポートには表示されます。また、どのサーバーが画像やサイズの大きいダウンロードを提供しているかはレポートでは示されません。

**構文と可能な値** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

There are no limitations on the *`server`* variable outside of the standard variable limitations.

**例** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**設定** {#section_969DB379D5BD469FBEE8D505D3000E49}

None

**注意事項、質問、ヒント** {#section_42A28F9B01574F38891D9D54B411D8FE}

The *`server`* variable can be used to show which domains are most popular or which servers are serving the most pages.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

変数と変数はコンバージョン変数です。

<!-- 

state.xml

 -->

これらの変数は、イベントを取り込む点で eVar と同様ですが、eVar とは異なり永続的ではありません。Folio Builder *`zip`* and *`state`* variables are like eVars that expire immediately.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 50 バイト | state | コンバージョン／訪問者プロファイル／訪問者の州 | "" |

Because the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events that are fired on the same page on which they are populated. For example, if you are using *`state`* to compare conversion rates by state, you should populate the *`state`* variable on every page of the checkout process. コンバージョンサイトでは、郵便番号のソースとして請求先住所の使用を推奨しますが、代わりに届け先住所を選択することもできます（注文の届け先住所が 1 つだけである場合）。メディアサイトでは、登録および広告クリックスルートラッキングのために、 *`zip`* and *`state`* for registration or ad click-through tracking.

**構文と可能な値** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

The *`state`* variable does not impose any special value or format restrictions. There are no limitations on *`state`* outside of the standard variable limitations.

**例** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**設定** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

None

**注意事項、質問、ヒント** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Populate *`state`* on every page that a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

この変数を使用すると、他のプラットフォーム用の AppMeasurement ライブラリと類似したヒットのタイムスタンプを指定できます。

<!-- 

timestamp.xml

 -->

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 4 バイト | 日時 | 直接レポートされません。 | データ収集サーバーによって設定されます。 |

**構文** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

The *`timestamp`* variable must be in the format explained in the next section.

>[!IMPORTANT]
>
>Your report suite must be timestamp-enabled by Customer Care before you can use the *`timestamp`* variable. After timestamp support is enabled, all hits sent to this report suite from JavaScript must have a timestamp manually set (using *`s.timestamp`*) or the hits will not be recorded.
>
>また、オフライントラッキングをサポートするためにレポートスイートのタイムスタンプサポートを有効にした場合は、JavaScript からこのレポートスイートに送られるすべてのヒットにもタイムスタンプが手動で設定（ *`s.timestamp`*). タイムスタンプ付きのヒットとタイムスタンプのないヒットを同じレポートスイートで記録することはできません。
>
>また、[タイムスタンプオプション](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F)設定を使用して、タイムスタンプのあるデータとないデータを同じグローバルレポートスイートで組み合わせたり、モバイルアプリからグローバルレポートスイートにタイムスタンプのあるデータを送信したり、新しいレポートスイートを作成することなくタイムスタンプを使用できるようにアプリをアップグレードしたりできます。

**タイムスタンプの形式** {#section_C12CBCECCD7047D38EF63A5800761CE9}

タイムスタンプには、UNIX（1970 年 1 月 1 日からの秒数）または ISO-8601 の形式を使用する必要があります。また、使用可能な ISO-8601 形式には次の制限があります。

* 日付と時刻を「T」で区切り、両方を指定する必要があります。
* 日付はすべて揃った暦日付（年、月および日）であることが必要です。. 曜日と年間通算日はサポートされません。
* 日付は、標準形式または拡張形式（`YYYY-MM-DD` または `YYYYMMDD`）が可能ですが、どちらの形式でも時間と分は含める必要があります。秒はオプションで `HH:MM`す(、、 `HH:MM:SS`、ま `HHMM`たは `HHMMSS`)。 分と秒の小数点以下の部分は、渡すことはできますが無視されます。

* An optional time zone can be specified in standard or extended format ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`, or Z)

UNIX タイムスタンプは引き続きサポートされます（1970 年 1 月 1 日からの秒数）。

**例** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

次のリストは、有効な ISO-8601 形式のタイムスタンプの例です。

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**設定** {#section_5275D206F2CB4009B3681E8C4457124A}

この変数を使用するには、カスタマーケアがレポートスイートでカスタムのタイムスタンプの受け入れを有効にする必要があります。カスタムのタイムスタンプを有効にしたら、レポートスイートに送信されるすべてのヒットにタイムスタンプを含める必要があります。この処理をおこなわないと、ヒットが破棄されます。

**注意事項、質問、ヒント** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* タイムスタンプは主に、モバイルプラットフォームでオフラインデータを追跡するために使用されます。通常、同じレポートスイートで Web データとオフラインアプリケーションデータの両方を収集しない限り、カスタムのタイムスタンプは無効にします。
* モバイル SDK でオフラインデータが有効になっている場合（デフォルト設定）、またはレポートスイートがタイムスタンプ付きのデータを承認するように設定されている場合、データにはタイムスタンプが付きます。モバイルデバイスでオフラインで収集されたデータは、データが発生した時点から数時間または数週間後に送信される可能性があります。これらのヒットは、タイムスタンプのないヒットよりも数分から数時間長く Analytics プラットフォーム内のキューに残ることがあります。

   * 送信されたタイムスタンプ付きのデータが現在の時間に非常に近いデータの場合、推定遅延は 10 ～ 15 分です。
   * 送信されたタイムスタンプ付きのデータが昨日のデータの場合、推定遅延は 2 時間です。
   * 送信されたタイムスタンプ付きのデータが昨日よりも古いデータの場合、遅延の進行が止まってから 1 日につき約 1 時間の遅延が加算されます（最大 15 日前まで）。

* タイムスタンプが有効なセッションデータは、最大 92 日間保持されます。

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

 変数は、イメージリクエストと cookie が書き込まれているドメインを指定するために、ファーストパーティ cookie の導入に使用されます。

<!-- 

trackingServer.xml

 -->

セキュリティ保護されていないページで使用されます。if *`trackingServer`* is defined, nothing goes to 2o7.net. If *`trackingServer`* is not defined (and dc is not defined), data goes to 112.2o7.net.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | "" |

アドビのデータセンターのリストについては、[ここ](https://helpx.adobe.com/analytics/kb/determining-data-center.html)を参照してください。

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

 変数は、イメージリクエストと cookie が書き込まれているドメインを指定するために、ファーストパーティ cookie の導入に使用されます。

<!-- 

trackingServerSecure.xml

 -->

セキュリティ保護されているページで使用されます。if *`trackingServerSecure`* is not defined, SSL data goes to *`trackingServer`*.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | "" |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

[!UICONTROL 統合データソース]では、[!UICONTROL transactionID] を利用して、オフラインデータをオンライントランザクション（オンラインで生成されたリードや購入など）に関連付けます。

<!-- 

transactionID.xml

 -->

アドビに送信される一意の *`transactionID`* をイメージリクエストの一部として送信しておくことで、トランザクションに関するオフライン情報の[!UICONTROL データソース]を後日アップロードした際にオンラインデータとの紐付けが可能になります。[データソース](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)を参照してください。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | xact | 該当なし | "" |

**トランザクションIDストレージの有効化**{#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Before *`transactionID`* values are recorded, [!UICONTROL Transaction ID Storage] must be enabled for the report suite selected in the Report Suite Manager. この設定は、次の場所にあります。

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

がレポートスイー *`transactionID Storage`* トに対して有効になっているかどうかを確認するには、

```
Analytics > Admin > Data Sources > Manage
```

**構文と可能な値** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

The *`transactionID`* should contain only alphanumeric characters. 複数の [!UICONTROL transactionID] を 1 回のヒットで記録する場合、コンマを使用して複数の値を区切る必要があります。

**例** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**注意事項、質問、ヒント** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* 記録が *`transactionID`* 有効になっていない場 *`transactionID`* 合、値は破棄され、統合データソースで使用で [!UICONTROL きなくなります]。 Make sure to set a conversion variable or event (an eVar or the events variable) on the page where *`transactionID`* is set. Otherwise, no data is recorded for the *`transactionID`*.

* 購入やリードな [!UICONTROL ど] 、複数のシステムのtransactionIDを記録する場合は、の値が常に一意であることを確 *`transactionID`* 認します。 これは、lead_1234 や purchase_1234 のように、ID にプレフィックスを追加することで実現できます。[!UICONTROL 統合データソースは] 、一意のデータが2回表示されると [!UICONTROL 、期待どおりに機能しません(データソースのデータは] 、間違ったデータに結び付け *`transactionID`* られます)。

* デフォルトでは、 *`transactionID`* 値は90日間記憶されます。 オフラインのインタラクションプロセスが 90 日を超える場合は、カスタマーケアにご連絡いただき、限度を延長してください。

>[!NOTE]
>
>The *`transactionID`* variable can contain any character other than a comma. 文字制限（最大 100 バイト）が指定される場所に配置されます。マルチバイト文字が使用されている場合、transactionID に予期しない文字が含まれるという問題が発生しないように、マルチバイト文字のサポートを有効にする必要があります。*`transactionID`*（名前をつけて保存）する必要があります。

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

ランダムで発行される ID の代わりに、 変数で任意のIDを指定することもできます

<!-- 

visitorID.xml

 -->

The *`visitorID`* can be up to 100 alpha-numeric characters and must not contain a hyphen.

カスタム ID を明示的に設定する場合は、常に他の ID メソッドの前に使用する必要があります。

使用順序は s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA です。

| ** 最大サイズ** | ** デバッガーパラメーター** | ** 入力されるレポート** | ** デフォルト値** |
|---|---|---|---|
| 100 バイト | vid | 該当なし | "" |

**構文と可能な値** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

>[!NOTE]
>
>The *`visitorID`* variable should not contain a hyphen.

**例** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**設定** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

None

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

 変数は、cookie が設定されているドメインを識別するために使用されます。

<!-- 

visitorNamespace.xml

 -->

If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. If *`visitorNamespace`* changes, all visitors reported in Analytics may become new visitors. また、訪問者履歴が現在および今後のトラフィックから切り離されます。アドビの担当者の許可がない場合は、この変数を変更しないでください。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | ns | 該当なし | "" |

Analytics では、サイトへの訪問者を一意に識別するために cookie を使用します。If *`visitorNamespace`* is not used, the cookie is associated 2o7.net. If *`visitorNamespace`* is used, the cookie is associated with a sub-domain of 2o7.net. サイトへのすべての訪問者の cookie は同じドメインまたはサブドメインに関連付ける必要があります。

この *`visitorNamespace`* 変数を使用するのは、ブラウザーの cookie 制限を超過しないようにするためです。Internet Explorer には、ドメインにつき 20 個の cookie までという制限があります。この *`visitorNamespace`* 変数を使用することによって、他社が使用している Analytics の cookie が貴社の訪問者の cookie と競合しなくなります。

**構文と可能な値** {#section_EE247FE371784CA4B6058182181F3EA1}

The value of *`visitorNamespace`* must be provided by Adobe and is a string of ASCII characters that don't contain commas, periods, spaces, or special characters.

```js
s.visitorNamespace="company_specific_value"
```

**複数レポートスイートでの訪問者の識別** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

If you do not specify a `visitorNamespace`, each report suite in your company receives its own visitor ID cookie written as `s_vi_[random string]`. `visitorNamespace` を指定した場合は、指定した `s_vi` にデータを送信するすべてのレポートスイートで、同じ `trackingServer` cookie が使用されます。マルチスイートタギングを導入している場合は、各レポートスイートで同一の cookie が使用されるように訪問者の名前空間を指定してください。

**例** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**設定** {#section_1128A2531ECC43DFA6749ECC21F050A2}

None

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

The  and  variables are conversion variables.

<!-- 

zip.xml

 -->

これらの変数は、イベントを取り込む点で eVar と同様ですが、eVar とは異なり永続的ではありません。The *`zip`* and *`state`* variables are like eVars that expire immediately.

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 50 バイト | zip | コンバージョン／訪問者プロファイル／郵便番号 | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. For example, if you are using *`zip`* to compare conversion rates by Zip Code, you should populate *`zip`* on every page of the checkout process. アドビでは、郵便番号のソースとして請求先住所を使用することを推奨します。代わりに、配送先住所を選択することもできます（注文の配送先住所が 1 つだけである場合）。メディアサイトでは、登録および広告クリックスルートラッキングのために、 *`zip`* and *`state`* for registration or ad click-through tracking.

**構文と可能な値** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

The *`zip`* variable does not impose any value or format restrictions. There are no limitations on *`zip`* outside of the standard variable limitations.

**例** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**設定** {#section_7987084EECC34DD38B643B94F82385CA}

None

**注意事項、質問、ヒント** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* [!UICONTROL zip ] は、関連イベントが発生するすべてのページ（チェックアウトプロセスの各ページなど）に設定します。
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

