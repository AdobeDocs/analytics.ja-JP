---
description: データソースでは、標準的なサーバー呼び出しとしてデータを処理する場合（汎用／フル処理）に、次の変数を使用できます。
seo-description: データソースでは、標準的なサーバー呼び出しとしてデータを処理する場合（汎用／フル処理）に、次の変数を使用できます。
seo-title: フル処理
solution: Analytics
subtopic: データソース
title: フル処理
topic: 開発者と導入
uuid: 590ae89c-6e17-453b- b701- ce1adbea6fa4
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# フル処理

データソースでは、標準的なサーバー呼び出しとしてデータを処理する場合（汎用／フル処理）に、次の変数を使用できます。

フル処理データソースのデータは、あたかも指定の時点で Adobe サーバーに受け取られたかのように処理されます（ヒットごとにタイムスタンプが付与されます）。

* [訪問者プロファイル](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8)
* [列リファレンス](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## 訪問者プロファイル {#section_6065627D0C144506965F562C80AE67F8}

フル処理データソースのデータは個別の訪問者プロファイルを使用して処理されるので、たとえアップロードされたデータ内の訪問者 ID が JavaScript やその他の AppMeasurement ライブラリを使用して収集されたデータと一致しても、eVar の割り当てに関しては訪問者プロファイルが関連付けられることはありません。

例えば、"user@example.com" という訪問者 ID を持つユーザーが、キャンペーン変数に格納されている、"Spring Sale"（スプリングセール）と名付けられたマーケティングキャンペーンを通してサイトを訪問したとします。後で同じ訪問者 ID を使用してトランザクションをアップロードした場合、"Spring Sale" キャンペーンは、フル処理データソースを使用してアップロードされたどのような売上イベントや成功イベントに対するクレジットも受け取ることはありません。

## 列リファレンス {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript 変数 </th> 
   <th colname="col2" class="entry"> フル処理列の変数 </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campaign </p> </td> 
   <td colname="col2"> <p>campaign </p> </td> 
   <td colname="col3"> <p>コンバージョンキャンペーンのトラッキングコード。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>channel </p> </td> 
   <td colname="col2"> <p>channel </p> </td> 
   <td colname="col3"> <p>チャネル文字列（例：「スポーツセクション」） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>注意：この変数は、標準のデータソースでも <code>currency code</code> としてサポートされています。 </p> </td> 
   <td colname="col3"> <p>売上高の通貨コード（例：USD）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timestamp </p> </td> 
   <td colname="col2"> <p>date </p> </td> 
   <td colname="col3"> <p><code>YYYY-MM-DDThh:mm:ss±UTC_offset</code> という ISO 8601 の日付フォーマット（例：<code>2013-09-01T12:00:00-07:00</code>）、または Unix の時刻フォーマット（1970 年 1 月 1 日からの経過秒数）を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>N</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>N</i>（例：&lt;eVar2&gt;…&lt;/eVar2&gt;） </p> </td> 
   <td colname="col3"> <p>コンバージョン eVar 名。最大 75 個の eVar（<span class="varname"> eVar1 </span> ~ <span class="varname"> eVar75 </span>）。 </p> <p>eVar 名（eVar12 など）や、わかりやすい名前（Ad Campaign 3 など）を指定できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>events </p> </td> 
   <td colname="col2"> <p>events </p> </td> 
   <td colname="col3"> <p>イベント文字列。書式設定には <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html" format="https" scope="external">s.events</a> 変数と同じ構文を使用しています。 </p> <p>次に例を示します。 </p> 
    <code>scAdd、event1、event7 </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hier<i>N</i> </p> </td> 
   <td colname="col2"> <p>hier<i>N</i>（例：&lt;hier2&gt;…&lt;/hier2&gt;） </p> </td> 
   <td colname="col3"> <p>階層名。最大 5 つの階層を使用できます（ <span class="varname"> hier1</span> ～ <span class="varname">hier5 </span>). </p> <p>デフォルトの階層名（「<span class="varname">hier2</span>」）や、わかりやすい名前（「<span class="term">Yankees</span>」）を指定できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>リンク名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>リンクのタイプ。次の値がサポートされています。 </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b>：ダウンロードリンク </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b>：離脱リンク </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b>：カスタムリンク </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>リンクの HREF（リンク先 URL）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>ページ名 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>ページタイプ（例：「エラーページ」） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageURL </p> </td> 
   <td colname="col2"> <p>pageURL </p> </td> 
   <td colname="col3"> <p>Page URL (for example, <code>https://www.mysite.com/index.html)</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>products </p> </td> 
   <td colname="col2"> <p>products </p> </td> 
   <td colname="col3"> <p>製品リスト（例：<code>"Sports;Ball;1;5.95"）</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 ～ prop75 </p> </td> 
   <td colname="col2"> <p>prop<i>N</i>（例：&lt;prop2&gt;…&lt;/prop2&gt;） </p> </td> 
   <td colname="col3"> <p>プロパティ番号の文字列（例： <span class="term"> スポーツセクション </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>購入 ID 番号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>ヒットを含めるレポートスイート ID（複数可）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server </p> </td> 
   <td colname="col2"> <p>server </p> </td> 
   <td colname="col3"> <p>サーバー文字列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>state </p> </td> 
   <td colname="col2"> <p>state </p> </td> 
   <td colname="col3"> <p>コンバージョンの州の文字列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>コンバージョンの郵便番号。 </p> </td> 
  </tr> 
 </tbody> 
</table>

JavaScript ライブラリを使用したときに自動的に入力されるトラフィック変数を、次の表に示します。これらのプロパティは関連する変数がありませんが、データソースを使用してインポートすることができます。

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>フル処理列の変数 </p> </th> 
   <th colname="col2" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>ピクセル単位のブラウザーの高さ（例：768）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>ピクセル単位のブラウザーの幅（例：1024）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charSet </p> </td> 
   <td colname="col2"> <p>Web サイトでサポートされる文字セット。UTF-8、ISO-8859-1 などがあります。 </p> <p>完全なリストを確認するには、「<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/multibyte/index.html" format="https" scope="external">2 バイト文字セット</a>（インターナショナリゼーション）」のホワイトペーパーを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>Visitor Click Map のオブジェクト識別子（oid） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>Visitor Click Map のオブジェクト識別子タイプ（oidt） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>Visitor Click Map のページ識別子（pid） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>Visitor Click Map のページ識別子タイプ（pidt） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>Visitor Click Map のソースインデックス（oi） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>Visitor Click Map のオブジェクトタグ名（ot） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>ビット単位の画面の色（例：24）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>訪問者の接続タイプ（<span class="term"> lan </span> また <span class="term"> はmodem </span>）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>訪問者側でファーストパーティセッション cookie がサポートされているかどうか（Y または N）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>Web サイトで使用するデフォルトの通貨コード。 </p> <p>USD（US ドル）、EUR（ユーロ）、JPY（日本円）など。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>現在のページが訪問者のホームページであるかどうか（Y または N）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>訪問者側で Java が有効かどうか（Y または N）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>JavaScript のバージョン（例：1.3）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugins </p> </td> 
   <td colname="col2"> <p>ブラウザーのプラグイン名をセミコロンで区切ったリスト。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>プロパティのプロパティ値。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>referrer </p> </td> 
   <td colname="col2"> <p>ページリファラーの URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resolution </p> </td> 
   <td colname="col2"> <p>画面の解像度（例：1024x768）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>マーケティングレポートの XML リクエストのバージョン番号（例：1.0）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timezone </p> </td> 
   <td colname="col2"> <p>訪問者のタイムゾーンの GMT との時差（例：-8）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>訪問者 ID 番号。 </p> </td> 
  </tr> 
 </tbody> 
</table>

