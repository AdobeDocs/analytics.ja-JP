---
description: レガシー JavaScript H コードのこれまでのリリースノートです。
seo-description: レガシー JavaScript H コードのこれまでのリリースノートです。
seo-title: JavaScript H コード - レガシー
solution: Analytics
subtopic: リリースノート
title: JavaScript H コード - レガシー
topic: 開発者と導入
uuid: 4586b250-0f1b-45b8-829c-18dc1201956f
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# JavaScript H コード - レガシー{#javascript-h-code-legacy}

レガシー JavaScript H コードのこれまでのリリースノートです。

>[!NOTE]
>
>To find the current library version, use [DigitalPulse Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=debugger_about).

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## H.27.5 - Update {#section_DB9535C7EC4A4DDE9BA56B6C02BE8327}

リリース日：**2016 年 6 月 17 日**

訪問者 API 1.5.7 を同梱しました。

## H.25.5 - Update {#section_B10151D7718F4568AE523BE1553FCCB7}

リリース日：**2016 年 5 月 20 日**

Visitor API 1.5.5 を同梱しました。

## H.27.5 - Update {#section_AD73ECD5CDAB4E158B509BA7B4B8CC1F}

リリース日：**2015 年 11 月 6 日**

* Visitor API 1.5.3 を同梱しました。

## H.27.5 - Update {#section_8A94D8A74A39486AAE248A22D661A261}

リリース日：**2015 年 9 月 18 日**

* Visitor API 1.5.2 を同梱しました。

## H.27.5 - Update {#section_62D1787F90FB4730B5F0C79EC1EF84B1}

リリース日：**2015 年 8 月 21 日**

* Visitor API 1.5.1 を同梱しました。

## H.27.5 - Update {#section_F58AF8B7FAE9470ABCBF2AAD9E7AF881}

リリース日：**2015 年 6 月 19 日**

* Visitor API 1.5 を同梱しました。

## H.27.5 - Update {#section_B3E310AFF909480BAD59A7F87D298348}

リリース日：**2015 年 5 月 22 日**

* Visitor API 1.4 を同梱しました。

## H.27.5 - Update {#section_E7006FC903064376A85D3EC2AC1D2544}

リリース日：**2015 年 4 月 17 日**

* Added Integrate module to s_code.js in legacy [!DNL AppMeasurement] for [!DNL JavaScript] H.X ZIP file. （AN-101001）

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

リリース日：**2015 年 2 月 20 日**

* Visitor API 1.3.5 を同梱しました。
* 最初のトラッキングコールの後、自動リファラートラッキングを実行しないように変更されました。これにより、最初のトラッキングコールの前に *`s.referrer`* が手動で設定された場合に、2 回目、3 回目などのトラッキングコール（通常はリンクトラッキング）で、リファラーを二重にカウントしなくなります。（AN-92647）

## H.27.4 - Update {#section_ED38D59E83B4417180877F7C10BE4582}

リリース日：**2015 年 1 月 16 日**

* 配布 zip を更新して Visitor API 1.3.4 を含めました。

リリース日：**2014 年 9 月 19 日**

* `tagContainerMarker` 変数が追加されました。これにより、区切りのダッシュ文字と共にバージョン文字列に追加される最大 4 文字を指定して導入できます。これは、Dynamic Tag Management で使用されます。

```js
  //  
<keyword>
  JavaScript 
</keyword> 
  s.tagContainerMarker = "D1.0"; 
    
  // Data Collection request 
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
```

## H.27.3 {#section_B38C61EE3BEA49CAA7A664395C85E4CF}

リリース日：**2014 年 8 月 22 日**

* 今後追加される機能をサポートするために、コードの内容を一部変更しました。

## H.27.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

リリース日：**2014 年 6 月 20 日**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* 訪問者 ID サービス 1.3 の新機能がサポートされました。

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

リリース日：**2014 年 6 月 12 日**

* Fixed an issue in the [!DNL Analytics] for [!DNL Target] integration that caused some hits to incorrectly be merged.

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

リリース日：**2014 年 5 月 23 日**

* [Marketing Cloud 訪問者 ID サービス](https://marketing.adobe.com/resources/help/en_US/mcvid/)がサポートされます。
* [Target と Analytics の統合](https://marketing.adobe.com/resources/help/en_US/target/a4t/) がサポートされます。

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

リリース日：**2013 年 10 月 18 日**

* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

リリース日：**2013 年 7 月 19 日**

* 自動リンク追跡でハッシュ／フラグメントが無視されるようになりました。Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

現在はハッシュ／フラグメントが無視されるので、ファイル名の拡張子が一致する場合にのみリンクが追跡されます。

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

リリース日：**2013 年 4 月 30 日**

* `useForcedLinkTracking`カスタムリンクコードを使用した手動リンクトラッキング[で説明している ](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_manuallinktrackcustomlink) オプションが Firefox 20 以降にも適用されるようになりました（以前は WebKit ブラウザーにのみ適用されました）。

* 画像オブジェクトの ID 生成がインスタンス間で一意になりました。そのため、同じページ上に複数のインスタンスがある場合の衝突を防ぐことができます。

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

リリース日：**2013 年 4 月 20 日**

* Fixed an issue in forced link tr [!DNL Windows]acking that caused a [!DNL JavaScript] error on some [!DNL Android] 2.2 Devices.

*  Media Player のビデオ自動トラッキングで、再生時間が正確にトラッキングされなかったスクラビングの問題が修正されました。

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

リリース日：**2013 年 2 月**

* Changed automatic exit link tracking to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

* `useForcedLinkTracking` の影響を受けるクリックイベントの範囲を絞り込みました。自動強制のリンクトラッキングは、次の場合にのみ適用されます。

   * `<A>` および `<AREA>` タグ

   * タグに `HREF` 属性が含まれている必要がある
   * `HREF` " `#``about:``javascript:`

   * `TARGET` 属性を設定しない、または現在 `TARGET` のウィンドウ（ `_self`、 `_top`または値 `window.name`）を参照する必要がある

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

リリース日：**2013 年 1 月**

* アドビのデータ収集サーバーのページ URL フィールドのサイズ拡大に対応するために、255 バイトを超える URL の送信のサポートを追加しました。Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. これにより、ブラウザーを切り捨てる場合に長い URL が他のデータより優先されないようにする一方、長い URL の収集を引き続き有効にすることができます。

* `escape` と `encodeURIComponent` を組み合わせて使用しエンコードされた文字列の URL デコードの処理を修正しました。

* WebKit ブラウザーで、ページの最初のサーバーコールがタイムアウトした場合、リンクの追跡に失敗する問題を修正しました。
* 訪問者の新たな識別方法が追加されました。[個別訪問者の識別](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors)を参照してください。
* `abort` フラグを新しく追加しました。このフラグは `doPlugins` 内で設定できます。このフラグを true に設定すると、対象のトラッキング呼び出しで [!DNL AppMeasurement] ライブラリが続行しません。abort フラグはあらゆるトラッキング呼び出しによってリセットされるので、後続のトラッキング呼び出しも中止する必要がある場合は、このフラグを再度 `doPlugins` 内に設定する必要があります。

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

これにより、追跡したくないアクティビティ（ディスプレイ広告内の一部のカスタムリンクや外部リンクなど）の識別に使用するロジックを一元管理することができます。

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

リリース日：**2012 年 10 月**

* [!DNL JavaScript] バージョンレポートでの追加バージョン番号のレポートのサポートを追加しました。従来はバージョンが 2 文字まで（例：1.8）に制限されていましたが、3 文字のバージョン番号（例：1.8.5）を使用できるようになりました。
* Fixed an issue with [!DNL Tag Manager] that prevented repeated values in Dependant Code blocks from being sent.

## H.25.1 {#section_680CE31CFA9945978F42612B684DB831}

リリース日：**2012 年 9 月**

* 以下の文字に対して URL エンコーディングを強制的に行うようにしました。

```
  ~ 
  ! 
  * 
  ( 
  ) 
  '
```

This resolves issues with un-escaped characters being stored in the [!DNL ClickMap] `s_sq` cookie.

* カスタムの `media.monitor` メソッドを使ってメディア終了イベントを追跡すると、ビデオ完了イベントが送信されないことがありましたが、この問題が修正されました。

```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

リリース日：**2012 年 7 月**

WebKit ブラウザー（Safari および Chrome）でリンクトラッキングが正常に完了するように更新されました。この更新により、自動的に追跡されるダウンロードリンクおよび離脱リンク（`s.trackDownloadLinks` および `s.trackExternalLinks` で指定）は正常に追跡されるようになりました。If you are tracking custom links using manual [!DNL JavaScript] calls, you need to modify how these calls are made.

例えば、離脱リンクおよびダウンロードリンクは、多くの場合次のようなコードを使用して計測されています。

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

Firefox および Internet Explorer では、リンクトラッキングが実行され新しいページが開きます。一方、WebKit ブラウザーでは、新しいページが開くとリンクトラッキングの実行がキャンセルされる場合があります。そのため、WebKit ブラウザーの場合、リンクトラッキングが完了しないことがあります。

これに対応するために、H.25 ではリンクトラッキングメソッド（`s.tl`）で指定できるオプションを追加し、WebKit ブラウザーにリンクトラッキングの完了を強制的に待機させます。この新しいメソッドでは、リンクトラッキングを実行後、デフォルトのブラウザーのアクションを使用せずにナビゲーションイベントとして処理します。そのためには、`doneAction` パラメーターを追加し、リンクトラッキングが完了したときにおこなうアクションを指定する必要があります。

`s.tl` の記述を次のように変更し、リンクトラッキング後に実行すべき関数名または「navigate」という文字列を 5 つめの引数である `doneAction` パラメーターとして指定してください。

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

`doneAction` として渡された 'navigate' は実行すべきオリジナルの関数名ではなく事前定義された特殊な文字列であり、トラッキングが完了した後に、`href` 属性で指定された URL が開くようになります。

次の表で、この機能をサポートするために H.25 で追加した設定変数とアップデートについて説明します。

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>変数 </p> </th> 
   <th colname="col2" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>useForcedLinkTracking </p> </td> 
   <td colname="col2"> <p>このフラグは、WebKit ブラウザーでの強制のリンクトラッキングを無効にする場合に使用します。強制のリンクトラッキングは、WebKit ブラウザーではデフォルトで有効で、他のブラウザーでは無視されます。 </p> <p> <b>デフォルト値</b> </p> <p> <code> true </code> </p> <p> <b>例</b> </p> 
    <code class="syntax javascript">s. useForcedLinkTracking&amp; amp;nbsp;= amp;nbsp;false </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forcedLinkTrackingTimeout </p> </td> 
   <td colname="col2"> <p><code>s.tl</code> に渡された <code>doneAction</code> の実行前に、トラッキングの完了を待機する時間（ミリ秒）の最大値。この値によって、最大の待機時間が指定されます。このタイムアウトの前にリンクトラッキングが完了した場合は、<code>doneAction</code> が直ちに実行されます。リンクトラッキングが未完了になっている場合は、このタイムアウト時間を長くする必要があると考えられます。 </p> <p> <b>デフォルト値</b> </p> <p>250 </p> <p> <b>例</b> </p> 
    <code class="syntax javascript">s. forcedLinkTrackingTimeout&amp; amp;nbsp;= amp;nbsp;500 </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink（<code>s.tl</code>） </td> 
   <td colname="col2"> <p>離脱リンクとダウンロードリンク、カスタムリンクを追跡します。WebKit ブラウザーでのリンクトラッキングの完了後にどのナビゲーションアクションを実行するかを指定するオプションのパラメーターとなります。 </p> <p> <b>構文</b> </p> 
    <code class="syntax javascript">s. tl（linkObject， linkType， linkName， variableOverrides， doneAction） </code>
  <p> <b>doneAction</b>：（オプション）リンクトラッキングの送信後、またはリンクトラッキングのタイムアウト（<code>s.forcedLinkTrackingTimeout</code> での指定値による）後に実行するアクションを指定します。<code>doneAction</code> に 'navigate' という文字列を指定すると、このメソッドによって <code>document.location</code> に <code>linkObject</code> の <code>href</code> 属性が設定されます。また、<code>doneAction</code> に関数を指定し、高度なカスタマイズを行うこともできます。 </p> <p>If providing a value for <code> onclick </code> in an anchor <code> false </code> event, you must return <code> s.tl </code> after the <code> href </code> call to prevent the default browser navigation. </p> <p> To mirror the default behavior and follow the URL specified by the <code> doneAction </code> attribute, provide a string of 'navigate' as the <code> doneAction </code>. </p> <p>Optionally, you can provide your own function to handle the navigation event by passing this function as the <code>$1</code>. </p> <p> <b>例</b> </p> 
    <code class="syntax javascript">&lt; a&amp; amp;nbsp;href="…」&amp; amp;nbsp;onclick="s. tl（this，'o'，'myLink'， null，'navigate'）;return&amp; amp;nbsp;false"&gt;クリックamp;nbsp;ここに&lt;/a&gt; </code><code class="syntax javascript">


&lt; a&amp; amp;nbsp;href="#"&amp; amp;nbsp;onclick="s. tl（this，'o'，'myLink'， null， function（）{if（'reset?'））document.location=...});return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; 
    </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

リリース日：**2012 年 4 月**

このアップデートは、すべてのお客様に推奨されます。

* Google Chrome Prerender（[https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender)）を使用してページが事前にレンダリングされているかどうかを検出できるように改良されました。Since Prerender loads and executes [!DNL JavaScript] and other code, this could result in page views being sent before a user clicks to visit your site. [!DNL JavaScript] ライブラリは、ユーザーがこれらの事前にレンダリングされたページのサーバーコールを送信するまで待機するようになりました。
* タイムスタンプデータをその他の ライブラリと同じような形式にカスタマイズするために、 ライブラリに `timestamp`[!DNL JavaScript] 変数を追加しました。[!DNL AppMeasurement]

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

リリース日：**2012 年 2 月**

* Javascript `Object.prototype` オーバーライドを使用している場合に、画像リクエストに余分なデータが含められる問題を修正しました。コンテキストデータ変数の処理時には、`Object.prototype` を使用している箇所をすべて無視するようにしました。
* 場合によって `pe` クエリパラメーターが同じ値で 2 回渡されることがある問題を修正しました。
*  の [!DNL ClickMap][!DNL JavaScript] トラッキングを修正し、body タグに `onClick` イベントハンドラーが指定されている場合も body タグのクリックが無視されるようになりました。
* Light Server Call（`trackLight`）で使用できる変数にタイムスタンプを追加しました。

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

リリース日：**2012 年 1 月**

* v15 の新しいビデオトラッキングで、再生完了（Video Completes）を手動または自動で計測するための新しい s.Media.complete() メソッドが利用できるようになりました。
* Fixed an issue that caused an "Attribute only valid on v:image" [!DNL JavaScript] error for `OnClick` events on VML elements in IE.
* コンテキストデータ変数が `linkTrackVars` で参照されているにもかかわらず、この変数がリンクサーバーコールに含まれないバグを修正しました。コンテキストデータ変数は処理ルールで使用されます。

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

リリース日：**2011 年 11 月**

* 同時に発生するセグメントとマイルストーンのヒットが結合されるようにビデオトラッキングを更新しました。

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

リリース日：**2011 年 11 月**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

リリース日：**2011 年 11 月**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

リリース日：**2011 年 10 月**

* Fixed an issue that caused the `linkTrackVars=none` and `linkTrackEvents=none` settings to not apply when using automatic exit link tracking. これらの設定が自動離脱リンクに適用されるようになったので、離脱リンク画像リクエストと共に prop や eVars、イベントが送信されることがなくなりました。

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

リリース日：**2011 年 9 月**

* ワイヤレスマークアップ言語（WML）の規格に準拠するために、モバイルデバイス上の画像タグから境界線の属性を削除しました。これにより、一部のモバイルデバイスでのレンダリングの問題が修正されました。

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

リリース日：**2011 年 8 月**

ビデオトラッキングでパーセントが正確に測定されるよう修正しました。

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

リリース日：**2011 年 7 月**

*  [!DNL Adobe Tag Manager].

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

リリース日：**2011 年 6 月**

* Fixed an issue that caused [!DNL JavaScript] errors when accessing certain properties of Vector Markup Language (VML) shape elements.
* 255 文字を超える参照文字列が、クエリ文字列ではなくパスの短縮によって切り捨てられるようになりました。これにより、クエリ文字列パラメーターが切り捨てられ収集されない問題が修正されました。

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

リリース日：**2011 年 5 月**

* ビデオトラッキング（pev3）変数が送信されない問題を修正しました。
* `s_gi` の呼び出し時に、コードを G コードと H コードの両方に互換させることができない問題を修正しました。この呼び出しの 2 番目のパラメーターに「1」を渡すと、コードはどちらのバージョンにも互換できるように設定されます。

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

リリース日：**2011 年 4 月**

* サーバー側の処理ルールを駆動する contextData のサポートを追加しました（v15 のみ）。
* Light Server Call のサポートを追加しました（v15 のみ）。
* イベントリスト内のカウンターイベントに「1」以外の値を割り当てられるようになりました。
* コンバージョン eVar とコンバージョンイベントを使用してビデオを追跡する新しいメソッドのサポートを追加しました（現在ベータ版のみ）。
* Media.trackWhilePlaying を false に設定するためのサポートを削除しました。この設定は常に true になります。
* 他のプラットフォームのように Firebug コンソールに送信するリクエストのログ記録を有効にするために debugTracking フラグを追加しました。
* どのブラウザーでも常に「+」が URL エンコードされるようになりました。
