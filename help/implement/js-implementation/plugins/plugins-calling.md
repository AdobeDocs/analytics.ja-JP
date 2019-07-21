---
description: JavaScript プラグインは通常 doPlugins 関数と呼ばれ、t() 関数が貼り付けるコードに呼び出される時に実行されます。
keywords: Analytics の導入
seo-description: JavaScript プラグインは通常 doPlugins 関数と呼ばれ、t() 関数が貼り付けるコードに呼び出される時に実行されます。
seo-title: doPlugins関数を使用したプラグインの呼び出し
solution: Analytics
subtopic: プラグイン
title: doPlugins関数を使用したプラグインの呼び出し
topic: 開発者と導入
uuid: 95dd01de-8136-4ec9- aac9-4a3d5371b839
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# doPlugins関数を使用したプラグインの呼び出し

JavaScript プラグインは通常 doPlugins 関数と呼ばれ、t() 関数が貼り付けるコードに呼び出される時に実行されます。

Consequently, if you set a variable in the *`doPlugins`* function, you can overwrite a variable you set on the HTML page. The only time the *`doPlugins`* function is not called is when the [!UICONTROL usePlugins] variable is set to 'false.'

## コード例 {#section_6940FD16F2E94753A1C39694D0CF5FBA}

The code example below is what the *`doPlugins`* function looks like in your JavaScript file:

JavaScript 版 AppMeasurement：

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
}
```

H コード：

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
 /* Add calls to plugins here */ 
} 
s.doPlugins=s_doPlugins
```

>[!NOTE]
>
>Hコードおよびそれ以前のバージョンでは、非常に古いブラウザー（IE4やIE5など）をサポートするために異なる構文を使用しています。

## Renaming the doPlugins Function {#section_70B7D58E057B48058E25907AB3726725}

*`doPlugins`* 関数は通常呼び出さ *`s_doPlugins`*&#x200B;れます。In certain circumstances, (usually when more than one version of code may appear on a single page) the *`doPlugins`* function name may be changed. If the standard *`doPlugins`* function needs to be renamed to avoid conflicts, ensure that *`doPlugins`* is assigned the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## doPlugins の使用 {#section_FA5D901CC5214D54BCD08AB77BED7925}

*`doPlugins`* この関数を使用すると、変数にデフォルト値を提供したり、サイトの任意のページの [!UICONTROL クエリ文字列パラメーター] から値を取得したりできます。Using *`doPlugins`* is often easier than populating the values in the HTML page because only one file must be updated. JavaScript ファイルへの変更はすぐに適用されない場合もあることに注意してください。サイトへのリターン訪問者は多くの場合、キャッシュしたバージョンの JavaScript ファイルを使用しています。つまり、ファイルに対する更新は、変更がおこなわれてから最大 1 か月はすべての訪問者に適用されない可能性があります。

The following example shows how the *`doPlugins`* function can be used to set a default value for a variable and to get a value from the query string.

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
 // if prop1 doesn't have a value, set it to "Default Value" 
 if(!s.prop1) 
s.prop1="Default Value" 
 
 // if campaign doesn't have a value, get cid from the query string 
 if(!s.campaign) 
s.campaign=s.getQueryParam('cid'); 
 
// Note: The code to read query parameters is different for  
// Appmeasurement for JavaScript since a plug-in is not required: 
// s.campaign=s.Util.getQueryParam('cid'); 
} 
```

## インストールされたプラグイン {#section_C5494347D85940A78670032199787CD0}

使用している JavaScript ファイルにプラグインが含まれ、利用可能かどうかを調べるには、JavaScript ファイルの[!UICONTROL プラグインセクション]を確認します。以下の例では、[!UICONTROL getQueryParam] 関数が示されています。

```js
/************************** PLUGINS SECTION *************************/ 
/* You may insert any plugins you wish to use here.                 */ 
/* 
 * Plugin: getQueryParam 1.3 - Return query string parameter values 
 */ 
s.getQueryParam=new Function("qp","d","" 
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```

