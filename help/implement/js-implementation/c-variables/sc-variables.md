---
description: Analytics には、Analytics データを収集するための変数が多数用意されています。例えば、pageName 変数の値は、レポートされる Web ページの名前になります。ここでは、AppMeasurement でサポートされる変数を示します。
keywords: Analytics Implementation;appmeasurement variables
subtopic: Variables
title: 変数の概要
topic: Developer and implementation
uuid: 067d0135-572a-4a44-af9e-445d3c4e9271
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 変数の概要

Analytics には、Analytics データを収集するための変数が多数用意されています。例えば、pageName 変数の値は、レポートされる Web ページの名前になります。ここでは、AppMeasurement でサポートされる変数を示します。

ページ変数について詳しくは、[こちら](/help/implement/js-implementation/page-variables/page-variables.md)を参照してください。
設定変数について詳しくは、[こちら](/help/implement/js-implementation/c-variables/configuration-variables.md)を参照してください。

## 変数の設定方法

AppMeasurement では、トラック関数 *`t()`* に最初の呼び出しをおこなう前に、すべての設定変数を設定する必要があります。*`t()`* への呼び出しの後に設定変数が設定されている場合、予期しない結果が発生する可能性があります。

設定変数は、*`doPlugins`* 関数内で設定されます。この関数は、track 関数の実行中に呼び出されます。この問題を引き起こす設定変数は、ClickMap のデータコレクションを有効にする *`trackInlineStats`* です。これにより、ClickMap モジュールは不確定な状態のままになり、その結果、最初のトラッキングコールで文字列「undefined」が Adobe Analytics ビーコンに追加されます。これは通貨コードに影響します。

この問題を解決するには、すべての設定変数を doPlugins 関数の上に移動します。

```
/************************** CONFIG SECTION **************************/ 
/* Ensure these variables are correct before deploying */ 
var s_account="[INSERT-REPORT-SUITE-ID-HERE]" 
var s=s_gi(s_account) 
s.trackingServer="[INSERT-TRACKING-SERVER-HERE]" 
s.visitorNamespace="[INSERT-VISITOR-NAMESPACE-HERE]" 
s.charSet="ISO-8859-1" 
s.currencyCode="USD" 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" 
s.linkInternalFilters="javascript:,three,two,one,dev16,.,nike" 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.debugTracking=true 
 
s.usePlugins=true; 
function s_doPlugins(s) { 
    //add your custom plugin code here 
} 
s.doPlugins=s_doPlugins; 
 
/* 
============== DO NOT ALTER ANYTHING BELOW THIS LINE ! =============== 
 
AppMeasurement for JavaScript version: 1.5.3 
Copyright 1996-2016 Adobe, Inc. All Rights Reserved 
More info available at https://www.omniture.com 
*/ 
function AppMeasurement(){var a=this;a.version="1.5.3";var k=window;k.s_c_in||(k.s_c_il=[],k.s_c_in=0);a._il=k.s_c_il;a._in=k.s_c_in;a._il[a._in]=a;k.s_c_in++;a._c="s_c";var q=k.AppMeasurement.zb;q||(q=null);var r=k,n,t;try{for(n=r.parent,t=r.location;n&&n.location&&t&&""+n.location!=""+t&&r.location&&""+n.location!=""+r.location&&n.location.host==t.host;)r=n,n=r.parent}catch(u){}a.ob=function(a){try{console.log(a)}catch(b){}};a.za=function(a){return""+parseInt(a)==""+a};a.replace=function(a,b,d){return!a|| 
0>a.indexOf(b)?a:a.split(b).join(d)};a.escape=function(c){var b,d;if(!c)return c;c=encodeURIComponent(c);for(b=0;7>b;b++)d="+~!*()'".substring(b,b+1),0<=c.indexOf(d)&&(c=a.replace(c,d,"%"+d.charCodeAt(0).toString(16).toUpperCase()));return c};a.unescape=function(c){if(!c)return c;c=0<=c.indexOf("+")?a.replace(c,"+"," "):c;try{return decodeURIComponent(c)}catch(b){}return unescape(c)};a.gb=function(){var c=k.location.hostname,b=a.fpCookieDomainPeriods,d;b||(b=a.cookieDomainPeriods);if(c&&!a.cookieDomain&& 
```

