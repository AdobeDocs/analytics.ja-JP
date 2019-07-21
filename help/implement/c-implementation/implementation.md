---
description: 'null'
seo-description: 'null'
seo-title: 導入ロードマップ
title: 導入ロードマップ
uuid: 988bcca5-67ae-4e3f-97e6-6a42030b1962
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 導入ロードマップ

## 新規ユーザー {#section_77433E4FC5ED4C6BAFC1E72EB61C4503}

Adobe Analytics を初めて利用する方は、[Adobe Analytics 使用の手引き](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/)を参考にして、最初の Analytics レポートスイート（データリポジトリ）をすばやく作成できます。Then, you can deploy Analytics code using [Experience Platform Launch](https://docs.adobelaunch.com/).

## 導入ロードマップ {#section_E3DD8D199B744FFB9E9B386A44220206}

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
   <td colname="col1"> 導入方法を選択します。 </td> 
   <td colname="col2"> <p>一般的な Analytics の実装方法は次のとおりです。 </p> <p> 
     <ul id="ul_A7475867861540EFBD77AEE8C6DAD418"> 
      <li id="li_035E2619670F4D04A7F708625A9C01EF"> <a href="https://docs.adobelaunch.com/" format="https" scope="external"> エクスペリエンスプラットフォームの起動 </a> （推奨） <p>アドビの Web サイトタグおよびモバイル SDK の管理機能を使用および導入する方法について、必要な情報がすべてまとめられています。 </p> </li> 
      <li id="li_996FA2F5B0E149399CED391AB5235D8A"> <a href="../../implement/c-implement-with-dtm/dtm-implementation-overview.md" format="dita" scope="local"> Dynamic Tag Management </a> <p>Dynamic Tag Management による Analytics の導入手順についての情報がまとめられています。 </p> </li> 
      <li id="li_18E6AD6D864246D0BA26DAA1D91DD811"> <a href="../../implement/js-implementation/javascript-implementation-overview.md" format="dita" scope="local"> JavaScript </a> <p>このガイドには、データ収集変数の説明と、JavaScript でのデータ収集コードの導入についての詳細が記載されています（<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js" format="https" scope="external">ビデオ</a>を含む）。 </p> </li> 
      <li id="li_85EC7A0AC5E04EE6981ED72A88C5D1FD"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="html" scope="external"> Analytics SDK </a> <p>Analytics SDK で以下を管理できます。 </p> <p> 
        <ul id="ul_F67F2E1964724800A84445A36DFB8E86"> 
         <li id="li_9C43F051EB5B4EA7A4C14EC1513DB824"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/analytics_main.html" format="html" scope="external"> iOS のモバイルアプリ </a> </li> 
         <li id="li_4354E44EB8B3494A88578C1621EF5BAC"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/analytics_main.html" format="html" scope="external"> Android のモバイルアプリ </a> </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> IDサービスを設定します。 </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p><code>VisitorAPI.js</code> の先頭部分に、以下の訪問者 ID 初期化コードを追加します。 </p> 
     <code class="syntax javascript">var visitor= Visitor. getInstance（"INSERT- MCORG- ID- HERE"）;
visitor. trackingServer="INSERT- TRACKING- SERVER- HERE";//をs. trackingServerと同じにする
visitor. trackingServerSecure="INSERT- SECURE- TRACKING- SERVER- HERE";//sameas s. trackingServerSecure
/*
============== DO NOT ALTER ANYTHING BELOW THIS LINE!========================================================================================================================================================================================================================================================== </code>
  
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> "INSERT- MCORG- ID- HERE" </code> -（必須） Adobe Experience Cloudのプロビジョニングを行うと、このAdobe Experience Cloud組織IDが管理者に送信されます。 </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code>"INSERT-TRACKING-SERVER-HERE"</code> -（必須）Analytics トラッキングサーバー。 </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code>"INSERT-SECURE-TRACKING-SERVER-HERE"</code> -（SSL が有効な場合に必須）Analytics セキュアトラッキングサーバー。ページのプロトコルがhttpsの場合にデータが送信されるトラッキングサーバーです。 </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> 選択した導入方法に沿ってページコードの更新とデプロイをおこないます。 </td> 
   <td colname="col2"> <p>ページコードは、トラッキング対象の各ページの開始 <code>&lt;body&gt;</code> タグの直後に挿入します。以下の変数は必ず更新してください。 </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code>s.pageName="INSERT-NAME-HERE" // 例：s.pageName=document.title var s_code=s.t();</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> 導入を検証します。 </td> 
   <td colname="col2"> <p> <a href="../../implement/impl-testing/impl-validation/impl-validation.md" format="dita" scope="local">テストと検証</a>には、導入を検証する方法についての情報がまとめられています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Adobe Experience Cloud デバッガーを使用して、データが送信されることを確認します。 </td> 
   <td colname="col2"> <p><a href="../../implement/impl-testing/debugger.md#topic_E05CEAF0682E483A9AB147D774CF2188" format="dita" scope="local"> Experience Cloudデバッガー </a>をインストールします。インストールしたら、ページコードを導入したページを読み込み、デバッガーを開きます。デバッガーに、送信された収集データの詳細情報が表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 詳細情報 {#section_64B6A948DF4A4B5E9E1D22549F8C508B}

[!UICONTROL Experience Platform Launch]、 [!UICONTROL Dynamic Tag Management]およびJavaScriptの各メソッドの違いについては、「実装方法 [の選択」を参照](../../implement/c-implementation-methods/choose-implementation-method.md#concept_97CE27B16410422EB28B4B9CE3B9529B)してください。

利用開始プロセスの概要と、最初の Analytics レポートスイートをすばやく設定するためのヘルプについては、Analytics 使用の手引きガイドの [Analytics 実装の手引き](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)を参照してください。
