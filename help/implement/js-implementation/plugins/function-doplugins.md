---
description: JavaScript プラグインは通常 doPlugins 関数と呼ばれ、t() 関数が貼り付けるコードに呼び出される時に実行されます。
keywords: Analytics の導入
seo-description: JavaScript プラグインは通常 doPlugins 関数と呼ばれ、t() 関数が貼り付けるコードに呼び出される時に実行されます。
seo-title: doPlugins 関数
solution: Analytics
subtopic: プラグイン
title: doPlugins 関数
topic: 開発者と導入
uuid: 367d5550- f8e2-477d-8681-18ae9665d699
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# doPlugins 関数

JavaScript プラグインは通常 doPlugins 関数と呼ばれ、t() 関数が貼り付けるコードに呼び出される時に実行されます。

その結果、`doPlugins` 関数内に変数を設定すると、HTML ページに設定した変数を上書きする場合があります。`doPlugins` 関数が呼び出されないのは、変数が *`usePlugins`* 設定されているとき `false`のみです。

**コード例**

`doPlugins` 関数は通常呼び出さ `s_doPlugins`れます。ただし、特定の場合（通常は単一のページに複数のバージョンの [!DNL Analytics] コードが表示される場合）には、`doPlugins` 関数名を変更できます。競合を避けるために標準 `doPlugins` 関数の名前を変更する必要がある場合、下の例に示されているように、`doPlugins` に正しい関数名を割り当てます。

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function  
<b>s_mc_doPlugins</b>(s_mc) { 
/* Add calls to plugins here */ 
} 
s_mc.doPlugins= 
<b>s_mc_doPlugins</b>
```

**doPlugins の使用**

この関数では、変数にデフォルトの値を受け渡す、またはサイトの任意のページにあるクエリ文字列パラメーターから値を取り出すことが簡単におこなえます。`doPlugins` を使うと更新するファイルが 1 つしかないため、HTML ページにある値を入力するより簡単になります。JavaScript ファイルに対する変更は必ずしも即座には反映されません。サイトへの再訪問問者は多くの場合、キャッシュしたバージョンの JavaScript を使っています。つまり、ファイルに対する更新は、変更がおこなわれてから最大 1 か月はすべての訪問者に適用されない可能性があります。

次の例では、`doPlugins` 関数を使って、変数にデフォルトの値を設定する方法、およびクエリ文字列から値を取得する方法について示しています。

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
/* Add calls to plugins here */ 
// if prop1 doesn't have a value, set it to "Default Value" 
if(!s.prop1) 
s.prop1="Default Value" 
 
// if campaign doesn't have a value, get cid from the query string 
if(!s.campaign) 
s.campaign=getQueryParam('cid'); 
} 
s.doPlugins=s_doPlugins
```

**インストールされたプラグイン**

使用している JavaScript ファイルにプラグインが含まれ、利用可能かどうかを調べるには、JavaScript ファイルの[!UICONTROL プラグインセクション]を確認します。次の例では、`getQueryParam`プラグインセクション[!UICONTROL で ] 関数がどのように表示されるかを示しています。

```js
/************************** PLUGINS SECTION *************************/ 
 
/* You may insert any plugins you wish to use here. */ 
/* 
* Plugin: getQueryParam 1.3 - Return query string parameter values 
*/ 
s.getQueryParam=new Function("qp","d","" 
+"vars=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```

