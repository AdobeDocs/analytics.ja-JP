---
description: JavaScript プラグインは通常 doPlugins 関数と呼ばれ、t() 関数が貼り付けるコードに呼び出される時に実行されます。
keywords: Analytics Implementation
subtopic: Plug-ins
title: doPlugins 関数を使用したプラグインの呼び出し
topic: Developer and implementation
uuid: 95dd01de-8136-4ec9-aac9-4a3d5371b839
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# doPlugins 関数を使用したプラグインの呼び出し

JavaScript プラグインは通常 doPlugins 関数と呼ばれ、t() 関数が貼り付けるコードに呼び出される時に実行されます。

その結果、*`doPlugins`* 関数内に変数を設定すると、HTML ページに設定した変数を上書きする場合があります。*`doPlugins`* 関数が呼び出されないのは、[!UICONTROL usePlugins] 変数が「false」に設定されている場合のみです。

## コード例 {#section_6940FD16F2E94753A1C39694D0CF5FBA}

以下のコード例は、JavaScriptファイルでの *`doPlugins`* 関数がどのようになるかを示します。

JavaScript 版 AppMeasurement:

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

> [!NOTE]一部の非常に古いブラウザー（IE 4 や IE 5 など）をサポートするために、H コード以前のバージョンでは別の構文を使用しています。

## doPlugins 関数の名前の変更 {#section_70B7D58E057B48058E25907AB3726725}

*`doPlugins`* 関数は通常、*`s_doPlugins`* と呼ばれます。ただし、特定の状況（通常は単一のページに複数のバージョンのコードが含まれる場合）では、*`doPlugins`* 関数名が変わることがあります。競合を避けるために標準 *`doPlugins`* 関数の名前を変更する必要がある場合、下の例に示されているように、*`doPlugins`* に正しい関数名を割り当てます。

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## doPlugins の使用 {#section_FA5D901CC5214D54BCD08AB77BED7925}

*`doPlugins`* 関数では、変数にデフォルトの値を受け渡すことや、サイトの任意のページにある[!UICONTROL クエリ文字列パラメーター]から値を取り出すことが簡単におこなえます。*`doPlugins`* を使用すると、更新する必要のあるファイルは 1 つだけなので、通常は HTML ページ内に値を設定するよりも簡単になります。JavaScript ファイルへの変更はすぐに適用されない場合もあることに注意してください。サイトへのリターン訪問者は多くの場合、キャッシュしたバージョンの JavaScript ファイルを使用しています。つまり、ファイルに対する更新は、変更がおこなわれてから最大 1 か月はすべての訪問者に適用されない可能性があります。

次の例では、*`doPlugins`* 関数を使って、変数にデフォルトの値を設定する方法、およびクエリ文字列から値を取得する方法について示しています。

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

