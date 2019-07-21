---
description: 現在のページ URL に指定したクエリ文字列パラメーターがある場合、その値を返します。重要なデータ（キャンペーントラッキングコード、内部検索キーワードなど）はページ上のクエリ文字列に含まれているので、getQueryParam は、データを取得して Analytics 変数に取り込むのに役立ちます。
keywords: Analytics の導入
seo-description: 現在のページ URL に指定したクエリ文字列パラメーターがある場合、その値を返します。重要なデータ（キャンペーントラッキングコード、内部検索キーワードなど）はページ上のクエリ文字列に含まれているので、getQueryParam は、データを取得して Analytics 変数に取り込むのに役立ちます。
seo-title: getQueryParam
solution: Analytics
subtopic: プラグイン
title: getQueryParam
topic: 開発者と導入
uuid: ba202756- c728-4ebc-8fd9-5bc29a9f673b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getQueryParam

現在のページ URL に指定したクエリ文字列パラメーターがある場合、その値を返します。重要なデータ（キャンペーントラッキングコード、内部検索キーワードなど）はページ上のクエリ文字列に含まれているので、getQueryParam は、データを取得して Analytics 変数に取り込むのに役立ちます。

>[!IMPORTANT]
>
>このプラグインはHコードのみで使用されます。[JavaScript版AppMeasurementは、この](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) 機能を、Util. getQueryParamを [使用してネイティブに提供](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)します。

Once installed in your [!DNL AppMeasurement] for JavaScript code, the plug-in is configured by selecting a [!DNL Analytics] variable to populate using data found in the query string, and specifying which query string values to capture. プラグインは、指定したクエリ文字列があればそれを検出し、選択した変数にその値を入力します。クエリ文字列パラメーターがその値で見つからない場合、空の文字列が返されます。If a query string parameter exists but does not have a value (such as param1 in `?param1&param2=value`), the word *`true`* is returned.

>[!NOTE]
>
>The base code for the plug-in must be installed in your [!DNL AppMeasurement] for JavaScript code before the examples below will work.

*`s.campaign`**`cid`* クエリパラメータの値として使用できるキャンペーントラッキングコードを取り込むには、 *`doPlugins()`* JavaScriptコード [!DNL AppMeasurement] の次の関数に入力します。

`s.campaign=s.getQueryParam('cid')`

In this example, if the user arrived at a landing page on your site where the URL was [!DNL https://www.yoursite.com/index.html?cid=123456], then *`s.campaign`* would receive a value of *123456*. これは [!DNL DigitalPulse] Debugger で確認でき、イメージリクエストの一環として *v0=123456* と表示されます。

>[!NOTE]
>
>The parameter *`cid`* and others are used here as examples. これらは、サイトに存在する任意のクエリ文字列パラメーターで置き換えることができます。

"*`getQueryParam`* プラグインには、Analytics 変数にデータを取り込める引数がさらに 2 つあります（オプション）。

```js
s.getQueryParam('p','d','u') 
 
where: 
p = comma-separated list of query parameters to locate (can also be a single value with no comma) 
d = delimiter for list of values (in case more than one specified parameter is found) 
u = where to search for value (e.g., document.referrer); set to current page URL by default
```

*p* がクエリ文字列パラメーターのリストで、URL に複数のクエリ文字列パラメーターがある場合、すべての値は区切りである *d* で分けられたリストで返されます。この区切りは、単一の文字または複数の文字（例えば「 : 」（スペース、コロン、スペース））にすることができます。*d* が省略された場合、値の間に区切りは使われません。1 つのクエリ文字列パラメーターが他のクエリ文字列パラメーターより優先される場合、下記の *if* ステートメントを使います。

```js
// cid takes precedence over iid if both exist in the query string 
s.campaign=s.getQueryParam('cid'); 
 if(!s.campaign) 
 s.campaign=s.getQueryParam('iid'); 
```

バージョン *`getQueryParam`* v2.0 からは、オプションとして 3 つ目の引数 *u* が許可されています。この引数では、クエリ文字列パラメーターの抽出元となる URL を指定できます。デフォルト（つまりこの 3 つ目の引数が省略または空白にされた場合）では、プラグインはページ URL を使用します。例えば、リファラーからクエリ文字列を抽出する場合、次のコードを使用できます。

```js
// take the query string from the referrer 
 s.eVar1=s.getQueryParam('pid','',document.referrer); 
```

必要なクエリ文字列パラメーターが現在のフレームの URL ではなくアドレスバーにある場合、フレームのあるこの 3 つ目の引数ではフラグ「f」を使います。

```js
// take the query string from the parent frame 
 s.eVar1=s.getQueryParam('pid','',f); 
```

フレームと *f* パラメーターを使う場合、*`getValOnce`* プラグインを使って、毎回のページビューでキャンペーントラッキングコードが送信されないようにすることが推奨されています。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

**プラグインコード**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
 /* Plugin Example: getQueryParam 2.3 
 //single parameter 
 s.campaign=s.getQueryParam('cid'); 
 
 //multiple parameters 
 s.campaign=s.getQueryParam('cid,sid',':'); 
 
 //non-page URL example 
 s.campaign=s.getQueryParam('cid','',document.referrer); 
 
 //parent frame example 
 s.campaign=s.getQueryParam('cid','','f'); 
 
 */ 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 None
```

