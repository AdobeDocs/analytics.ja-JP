---
description: 次のページビューで Analytics 変数の値を取り込みます。例えば、プラグインを使って前のページビューから s.pageName 値を取得して、カスタムトラフィック変数に取り込むことができます。指定した成功イベントがセットされた場合にのみ前の値を取得するオプションもあります。
keywords: Analytics の導入
seo-description: 次のページビューで Analytics 変数の値を取り込みます。例えば、プラグインを使って前のページビューから s.pageName 値を取得して、カスタムトラフィック変数に取り込むことができます。指定した成功イベントがセットされた場合にのみ前の値を取得するオプションもあります。
seo-title: getPreviousValue
solution: Analytics
subtopic: プラグイン
title: getPreviousValue
topic: 開発者と導入
uuid: 20da7b4a-9820-4690- a1cc- d10b6dd627a7
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPreviousValue

次のページビューで Analytics 変数の値を取り込みます。例えば、プラグインを使って前のページビューから s.pageName 値を取得して、カスタムトラフィック変数に取り込むことができます。指定した成功イベントがセットされた場合にのみ前の値を取得するオプションもあります。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## プラグインコードと導入 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**：このセクションでは変更は必要ありません。

**プラグイン構成**

次のコードを *`s_doPlugins()`* 関数 *`s_code.js`***&#x200B;を使用します。持続値データを取り込むために、1 つのカスタムトラフィック（s.prop）変数または 1 つのカスタムコンバージョン（s.eVar）変数を選択します。これは Admin Console を使って有効にした変数で、他の目的では使用されていないものを使います。次のサンプルは自分の条件に合わせて変更して使用できます。

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* には 3 つの引数があります。

1. The variable to be captured from the previous page ( *`s.pageName`* above).
1. The cookie name for use in storing the value for retrieval ( *`gpv_pn`* above).
1. The events that must be set on the page view in order to trigger the retrieval of the previous value ( *`event1`* above). 空白または省略された場合、プラグインはすべてのページビューで前の値を取り込みます。

**PLUGINS SECTION**：[!DNL s_code.js] ファイルにある PLUGINS SECTION という名称の領域に次のコードを追加します。プラグインコードのこの部分は一切変更しないでください。

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 
```

**メモ**

* 必ず、プラグインでデータの収集が希望どおりに実行されることを十分にテストし確認してから、実稼動環境に実装してください。
* 任意のページで選択した変数に値がない場合、*no value*&#x200B;というテキストが cookie に含まれます。
* これにより、各 cookie に 30 分の固定有効期限が設定され、毎回のページ読み込みでリフレッシュされます。プラグインは訪問の全期間で機能します。
* 関数はコードのプラグインセクションの一部として呼び出す必要があるため、コードは *`s.t()`* または *`s.tl()`* 呼び出されます。

* The chosen variable should be populated with a value prior to the call to *`s.getPreviousValue`*. *`s_doPlugins()`* この関数は、ページ上の変数の入力後に実行されるので、この問題は発生しません。It should only be a matter of concern if the variable used with this plug-in is populated within the *`s_doPlugins()`* function and after the call to *`s.getPreviousValue`*.

