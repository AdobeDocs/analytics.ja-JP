---
description: getVisitNum プラグインは、ユーザーがサイトを訪問した回数を判断し、その回数を Analytics 変数に取り込みます。
keywords: Analytics の導入
seo-description: getVisitNum プラグインは、ユーザーがサイトを訪問した回数を判断し、その回数を Analytics 変数に取り込みます。
seo-title: getVisitNum
solution: Analytics
subtopic: プラグイン
title: getVisitNum
topic: 開発者と導入
uuid: 27d57f92- fffb-44d0- b9ca-9da93323f64c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getVisitNum

getVisitNum プラグインは、ユーザーがサイトを訪問した回数を判断し、その回数を Analytics 変数に取り込みます。

## プラグインコードと導入 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**：このセクションでは変更は必要ありません。

**プラグイン構成**

次のコードを *`s_doPlugins()`* 関数 *`s_code.js`***&#x200B;を使用します。訪問回数データを取り込むために、1 つのカスタムトラフィック（s.prop）変数または 1 つのカスタムコンバージョン（s.eVar）変数を選択します。これは管理コンソールを使って有効にした変数で、他の目的では使用されていないものを使います。次のサンプルは自分の条件に合わせて変更して使用できます。

`s.prop1=s.getVisitNum();`

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

**PLUGINS SECTION**：[!DNL s_code.js] ファイルにある PLUGINS SECTION という名称の領域に次のコードを追加します。プラグインコードのこの部分は一切変更しないでください。

```js
/* 
* Plugin: getVisitNum - version 3.0 
*/ 
s.getVisitNum=new Function("tp","c","c2","" 
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}" 
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi" 
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!" 
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn=" 
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi" 
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els" 
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri" 
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);" 
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)" 
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}"); 
s.dimo=new Function("m","y","" 
+"var d=new Date(y,m+1,0);return d.getDate();"); 
s.endof=new Function("x","" 
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x==" 
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if(" 
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return " 
+"t;");
```

**パラメーター**

* tp =（文字列、オプション）トラッキング期間。日には "d"、週には "w"、月には "m" を使用します。独自の日数にはその数字を使用します。

   * 日、週または月が選択されている場合は、日／週／月の終わりに訪問回数がリセットされます。
   * 独自の日数が選択されている場合は、その日数の経過後に訪問回数がリセットされます。
   * 値が指定されていない場合は "m" が使用されます。

* c =（文字列、オプション）永続的な cookie 名を指定します。デフォルトは 's_vnum' です。
* c2 =（文字列、オプション）セッション cookie 名を指定します。デフォルトは 's_invisit' です。

**戻り値**

* 訪問回数（1、2、3 など）を返します。この数字は訪問時に最初にアクセスしたページでのみ増分されます。
* プラグインが訪問回数を特定できない場合（cookie がブロックされる場合）は、"訪問回数不明" を返します。

**例**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**メモ**

* 必ず、プラグインでデータの収集が希望どおりに実行されることを十分にテストし確認してから、実稼動環境に実装してください。
* このプラグインは、ユーザーの Web ブラウザーに cookie を設定できることを前提にしています。ユーザーが cookie を許可しない場合、すべての訪問は初回の訪問とみなされます。

