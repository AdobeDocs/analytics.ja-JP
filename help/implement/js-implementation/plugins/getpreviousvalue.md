---
description: 次のページビューで Analytics 変数の値を取り込みます。例えば、プラグインを使って前のページビューから s.pageName 値を取得して、カスタムトラフィック変数に取り込むことができます。指定した成功イベントがセットされた場合にのみ前の値を取得するオプションもあります。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPreviousValue
topic: Developer and implementation
uuid: 20da7b4a-9820-4690-a1cc-d10b6dd627a7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPreviousValue

次のページビューで Analytics 変数の値を取り込みます。例えば、プラグインを使って前のページビューから s.pageName 値を取得して、カスタムトラフィック変数に取り込むことができます。指定した成功イベントがセットされた場合にのみ前の値を取得するオプションもあります。

> [!NOTE]後述の説明では、実際のサイトに合わせてデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## プラグインコードと導入 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**：このセクションでは変更は必要ありません。

**プラグイン構成**

次のコードを *`s_doPlugins()`* 関数内に置いてください。この関数は、*`s_code.js`ファイルの* Plugin Config *という名称の領域にあります。*&#x200B;持続値データを取り込むために、1 つのカスタムトラフィック（s.prop）変数または 1 つのカスタムコンバージョン（s.eVar）変数を選択します。これは Admin Console を使って有効にした変数で、他の目的では使用されていないものを使います。次のサンプルは自分の条件に合わせて変更して使用できます。

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* には 3 つの引数があります。

1. 前のページから取り込む変数（上記の *`s.pageName`*）。
1. 取得用に値を格納するための cookie の名前（上記の *`gpv_pn`*）。
1. 前の値の取得をトリガーするためにページビューで設定する必要のあるイベント（上記の *`event1`*）。空白または省略された場合、プラグインはすべてのページビューで前の値を取り込みます。

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
* 関数はコードのプラグインセクションの一部として呼び出す必要があるため、コードは  *`s.t()`* または *`s.tl()`* が呼び出されるたびに実行します。

* 選択された変数は、*`s.getPreviousValue`* への呼び出しの前に、値を使用して生成する必要があります。*`s_doPlugins()`* 関数はページの変数に値が入力されてから実行されるため、この問題が生じることは極めてまれです。このプラグインで使用される変数が&#x200B;*`s_doPlugins()`* 関数内および *`s.getPreviousValue`* 呼び出し後に設定される場合にのみ、問題が発生する可能性があります 。

