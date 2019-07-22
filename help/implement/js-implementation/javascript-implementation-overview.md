---
description: Analytics の使用を開始するにあたって、レポートに表示するデータをレポートスイートに送信する必要があります。
keywords: Analyticsの導入;javascript;javascript実装;appMeasurement;ダウンロード測定、IDサービス;visitorapi. js;キャッシング;AppMeasurement圧縮
seo-description: Analytics の使用を開始するにあたって、レポートに表示するデータをレポートスイートに送信する必要があります。
seo-title: JavaScript導入の概要
solution: Analytics
title: JavaScript導入の概要
topic: 開発者と導入
uuid: bb661d8c- faf9-4454- ac3c-0c1a4c0a9336
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# JavaScript導入の概要

Analytics の使用を開始するにあたって、レポートに表示するデータをレポートスイートに送信する必要があります。

The easiest and recommended way to send data to [!DNL Analytics] is by using [Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md). 場合によっては、従来の JavaScript による導入方法を使用して Analytics を導入することが必要な場合もあります。

>[!NOTE]
>
>ここでは、Analyticsの導入方法について説明します。Analytics のすべてのお客様が [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) を利用することができます。これは、Experience Cloud タグを導入する標準の方法です。

## 実装手順 {#section_73961BAD5BB4430A95E073DE5C026277}

データを収集するコードをページに適切に導入するには、新しいファイルを Web サイトにアップロードするためにホストサーバーにアクセスできることが必要です。また、コードを導入するための既存のサイトがあると便利です。

以下の手順で、Analytics の基本的な導入方法を説明します。

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> 手順 </th> 
   <th colname="col1" class="entry"> タスク </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> JavaScript 版 AppMeasurement と訪問者 ID サービスをダウンロードします。 </td> 
   <td colname="col2"> <p>これは<a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=code_manager_admin" format="http" scope="external">コードマネージャー</a>でダウンロードできます。 </p> <p>ダウンロードするこの zip ファイルには、いくつかのファイルが含まれています。<code>AppMeasurement.js</code> および <code>VisitorAPI.js</code> は、Analytics の導入時に使用するファイルです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> IDサービスを設定します。 </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p><code>VisitorAPI.js</code> の先頭部分に、以下の訪問者 ID 初期化コードを追加します。 </p> 
     <code class="syntax javascript">var visitor= Visitor. getInstance（"INSERT- MCORG- ID- HERE"）;visitor. trackingServer="INSERT- TRACKING- SERVER- HERE";//s. trackingServer visitor visitor. trackingServerSecure="INSERT- SECURE- TRACKING- SERVER- HERE";//sameas s. trackingServerSecure/*== DO NOT ALTER ANYTHING BELOW THIS LINE== </code>  
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> "INSERT- MCORG- ID- HERE" </code> -（必須） Adobe Experience Cloudのプロビジョニングを行うと、このAdobe Experience Cloud組織IDが管理者に送信されます。 </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code>"INSERT-TRACKING-SERVER-HERE"</code> -（必須）Analytics トラッキングサーバー。 </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code>"INSERT-SECURE-TRACKING-SERVER-HERE"</code> -（SSL が有効な場合に必須）Analytics セキュアトラッキングサーバー。ページのプロトコルがhttpsの場合にデータが送信されるトラッキングサーバーです。 </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> <code>AppMeasurement.js</code> を更新します。 </td> 
   <td colname="col2"> <p><a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_4351543F2D6049218E18B48769D471E2" format="dita" scope="local">AppMeasurement.js のコード例</a>をコピーして、自分の <code>AppMeasurement.js</code> ファイルの先頭部分に貼り付けます。以下の変数は必ず更新してください。 </p> 
    <ul id="ul_62FA640BD2604E589650A92158272615"> 
     <li id="li_54E56B483B3A416EA27D7B540D60E39F"> <code>s.account="INSERT-RSID-HERE" var s=s_gi(s_account)</code> </li> 
     <li id="li_00A958289BB045379B436F13287E03D5"> <code> s.trackingServer="INSERT-TRACKING-SERVER-HERE" </code> </li> 
     <li id="li_C0779ADF780440ED876236AEB1FB5DCC"> <code> s.visitorNamespace = "INSERT-NAMESPACE-HERE" </code> </li> 
     <li id="li_93072B656C134D8C89195B7F2D7D8F05"> <code> s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE") </code> </li> 
    </ul> <p> See <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly populate the trackingServer and trackingServerSecure variable </a> or contact Client Care if you are unsure about any of these values. 正しく設定されていないと、実装によってデータが収集されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> <code>AppMeasurement.js</code> および <code>VisitorAPI.js</code> をホストします。 </td> 
   <td colname="col2"> <p>この 2 つのコア JavaScript ファイルは、サイトのすべてのページから参照可能な Web サーバーでホストする必要があります。次の手順で、このファイルへのパス情報が必要になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> すべてのサイトページで、<code>AppMeasurement.js</code> および<code>VisitorAPI.js</code> を参照します。 </td> 
   <td colname="col2"> <p> 各ページの <code>&lt;head&gt;</code> または &lt;body&gt; タグ内に次のコードを追加して、訪問者 ID サービスを含めます。<code>VisitorAPI.js</code> は <code>AppMeasurement.js</code> の前に含める必要があります。 </p> 
    <code class="syntax html">&lt; script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"&gt;&lt;/script&gt; </code>
  <p> 各ページの <code>&lt;head&gt;</code> タグまたは <code>&lt;body&gt;</code> タグに次のコードを追加して、JavaScript 版 AppMeasurement を含めます。 </p> 
    <code class="syntax html">&lt; script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"&gt;&lt;/script&gt; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> ページコードを更新し、導入します。 </td> 
   <td colname="col2"> <p><a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_042412C29CC249E298F19B2BC2F43CE7" format="dita" scope="local">ページコード例</a>をコピーして、トラッキング対象の各ページの開始 <code>&lt;body&gt;</code> タグの直後に貼り付けます。未使用の変数はセット不要です。以下の変数は必ず更新してください。 </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code>s.pageName="INSERT-NAME-HERE" // 例：s.pageName=document.title var s_code=s.t();</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step7_icon.png" id="image_A423CBF386AF4E5986E8CBB6E31CD3E5" /> </td> 
   <td colname="col1"> DigitalPulse Debugger を使用して、データが送信されることを確認します。 </td> 
   <td colname="col2"> <p>"<a href="../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2" format="dita" scope="local">Adobe Debugger</a> ブックマークレットをインストールします。インストールしたら、ページコードを導入したページを読み込み、デバッガーを開きます。デバッガーに、送信された収集データの詳細情報が表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## キャッシュ {#section_4E2D1D962DF046418134C43CFC49AD4A}

JavaScript ファイルは訪問者のブラウザーでの初回の読み込み後にキャッシュされます。通常、JavaScript ファイルは1 回のセッションで 2 回以上ダウンロードされることはありません。このファイルがサイトの各ページで使用されている場合でも、ページごとにダウンロードされることはありません。ほとんどの Web サイトでは、ユーザーは通常 1 回のセッションで複数のページを表示するので、何度も使用される JavaScript コードをこのファイルに記述しておくと、全体でダウンロードされるデータ量を削減できます。

## AppMeasurement 用 JavaScript の圧縮 {#section_C10BBC84C81C414088F97363D29E021B}

コアファイルのページの重さ（サイズ）が問題となっている場合（JavaScript 版 AppMeasurement 1.0 は事前に圧縮されています）、GZIP を使用してファイルを圧縮することを推奨します。GZIP はすべての主要なブラウザーでサポートされており、JavaScript の圧縮よりも高いパフォーマンスで、コア [!DNL s_code.js] JavaScript ファイルの圧縮と解凍が行われます。

次のリンクでは、サイトで GZIP の機能を使用して [!DNL s_code.js] JavaScript コードを圧縮する方法について説明しています。

[Apache モジュール mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Tomcat および Flex による gzip 圧縮の有効化](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
