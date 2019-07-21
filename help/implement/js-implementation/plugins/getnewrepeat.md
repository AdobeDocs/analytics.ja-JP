---
description: 訪問者が新規訪問者とリピーターのどちらであるかを判断し、その情報を Analytics 変数に取り込みます。
keywords: Analytics の導入
seo-description: 訪問者が新規訪問者とリピーターのどちらであるかを判断し、その情報を Analytics 変数に取り込みます。
seo-title: getNewRepeat
solution: Analytics
subtopic: プラグイン
title: getNewRepeat
topic: 開発者と導入
uuid: e3e9f362- e0b1-4a2b- bb5b-98eddaya0a7f4
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getNewRepeat

訪問者が新規訪問者とリピーターのどちらであるかを判断し、その情報を Analytics 変数に取り込みます。

このプラグインを使用すると次の質問に答えられます。

* 訪問者のうち、新規訪問者の割合（リピーターに対して）はどのぐらいか。
* リピーターは、新規訪問者に比べて人数あたりのコンバージョン数が高いか。その比率はどのぐらいか。
* 自社のキャンペーンは持続的な訪問をもたらしているか。例えば、キャンペーンでクリックスルーしたユーザーは、その後また訪問しているか。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## プラグインコードと導入 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**：このセクションでは変更は必要ありません。

**プラグイン構成**

次のコードを *`s_doPlugins()`* 関数 *`s_code.js`***&#x200B;を使用します。持続値データを取り込むために、1 つのカスタムトラフィック（s.prop）変数または 1 つのカスタムコンバージョン（s.eVar）変数を選択します。これは Admin Console を使って有効にした変数で、他の目的では使用されていないものを使います。次のサンプルは自分の条件に合わせて変更して使用できます。

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`* には 2 つのオプション引数があります。

1. 最初のオプション引数は cookie が継続する必要のある日数です。この引数が省略された場合のデフォルト値は 30 日です。
1. 2 つ目のオプション引数は cookie の名前です。この引数が省略された場合はデフォルト値が使われます。

**PLUGINS SECTION**：[!DNL s_code.js] ファイルにある PLUGINS SECTION という名称の領域に次のコードを追加します。プラグインコードのこの部分は一切変更しないでください。

```js
/* 
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat 
 */ 
s.getNewRepeat=new Function("d","cn","" 
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:" 
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length=" 
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct" 
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N" 
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}"); 
/* 
* Utility Function: split v1.5 (JS 1.0 compatible) 
*/ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");
```

必ず、プラグインでデータの収集が希望どおりに実行されることを十分にテストし確認してから、実稼動環境に実装してください。
