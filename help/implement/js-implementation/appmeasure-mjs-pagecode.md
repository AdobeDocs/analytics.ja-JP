---
description: ここでは、コア JavaScript ファイルおよびサイト上のページのコード例を紹介します。
keywords: Analytics Implementation;appmeasurement.js code;example page code
subtopic: JavaScript AppMeasurement
title: ページコードとグローバル設定の例
topic: Developer and implementation
uuid: e8880d77-172b-42e5-8187-ce371aa9eff9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# ページコードとグローバル設定の例

ここでは、コア JavaScript ファイルおよびサイト上のページのコード例を紹介します。

>[!IMPORTANT]
>
>この例では訪問者 ID サービスを使用していますが、このサービスは [JavaScript の実装](/help/implement/js-implementation/javascript-implementation-overview.md)の一部としてデプロイされます。訪問者 API JavaScript ファイルをすべてのサイトページに含める前に、AppMeasurement で訪問者 ID サービスを有効にすると、訪問者が二重にカウントされる可能性があります。訪問者の二重カウントを避けるには、「[訪問者 ID サービス](/help/implement/js-implementation/c-unique-visitors/visid-service.md)」に記載されているプロセスを理解して従うようにしてください。

## コード例：AppMeasurement.js {#section_4351543F2D6049218E18B48769D471E2}

>[!IMPORTANT]
>
>設定変数は、*`doPlugins`* 関数の上に設定する必要があります。

新規に実装する場合、最初に AppMeasurement.js の先頭に以下のグローバル設定コードを貼り付けます。

```js
//initialize AppMeasurement 
var s_account="INSERT-RSID-HERE" 
var s=s_gi(s_account) 
 
/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/ 
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE") 
 
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
 
/* uncomment below to use doPlugins */ 
/* s.usePlugins=true 
function s_doPlugins(s) { 
 
// use implementation plug-ins that are defined below 
// in this section. For example, if you copied the append 
// list plug-in code below, you could call: 
// s.events=s.apl(s.events,"event1",",",1); 
 
} 
s.doPlugins=s_doPlugins */ 
 
/* WARNING: Changing any of the below variables will cause drastic 
changes to how your visitor data is collected.  Changes should only be 
made when instructed to do so by your account manager.*/ 
s.trackingServer="INSERT-TRACKING-SERVER-HERE" 
s.trackingServerSecure="INSERT-SECURE-TRACKING-SERVER-HERE" 
 
/************************** PLUGINS SECTION *************************/ 
 
// copy and paste implementation plug-ins here - See "Implementation Plug-ins" @ 
// https://marketing.adobe.com/resources/help/en_US/sc/implement/#Implementation_Plugins 
// Plug-ins can then be used in the s_doPlugins(s) function above  
 
/****************************** MODULES *****************************/ 
 
// copy and paste implementation modules (Media, Integrate) here 
// AppMeasurement_Module_Media.js - Media Module, included in AppMeasurement zip 
// AppMeasurement_Module_Integrate.js - Integrate Module, included in AppMeasurement zip 
 
/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  
```

## ページコードの例 {#section_042412C29CC249E298F19B2BC2F43CE7}

新しい実装の場合、次のページコードを、追跡したいページの開始 <body> タグの直後に貼り付けることができます。

```js
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
var s_code=s.t();if(s_code)document.write(s_code)//--></script>
```

各ページに `AppMeasurement.js` と `VisitorAPI.js` への参照が含まれていることも必ず確認してください。「[JavaScript の実装](/help/implement/js-implementation/javascript-implementation-overview.md)」を参照してください。
