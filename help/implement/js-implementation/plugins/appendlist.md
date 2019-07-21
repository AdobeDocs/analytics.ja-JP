---
description: apl（または appendList）プラグインを使うと、任意のコンマ区切り形式のリストに値を付加できます。大文字と小文字の区別をするかしないかのオプションがあり、値がリストに存在しないことを確認するチェックもおこなえます。APL プラグインはいくつかの標準プラグインによって参照されますが、さまざまな状況で直接使うことができます。
keywords: Analytics の導入
seo-description: apl（または appendList）プラグインを使うと、任意のコンマ区切り形式のリストに値を付加できます。大文字と小文字の区別をするかしないかのオプションがあり、値がリストに存在しないことを確認するチェックもおこなえます。APL プラグインはいくつかの標準プラグインによって参照されますが、さまざまな状況で直接使うことができます。
seo-title: appendList
solution: Analytics
subtopic: プラグイン
title: appendList
topic: 開発者と導入
uuid: e923c86c- eaa6-4e17- a3a4-0e08af886674
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# appendList

apl（または appendList）プラグインを使うと、任意のコンマ区切り形式のリストに値を付加できます。大文字と小文字の区別をするかしないかのオプションがあり、値がリストに存在しないことを確認するチェックもおこなえます。APL プラグインはいくつかの標準プラグインによって参照されますが、さまざまな状況で直接使うことができます。

このプラグインは以下の目的で使用できます。

* 現在のイベント変数にイベントを追加する
* リストに重複する値がないことを確認しながらリスト変数に値を追加する
* ページロジックに基づいて現在の製品変数に製品を追加する
* 次のパラメーターに値を追加する：*`linkTrackVars`* および *`linkTrackEvents`*

**使用例 1**

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>シナリオ </p> </td> 
   <td colname="col2"> <p>イベントが重複しないことを確認しながら<span class="term"> event1 </span> を指定します。 </p> <p>s.events="scCheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コード </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>結果 </p> </td> 
   <td colname="col2"> <p>s.events="scCheckout,event1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**使用例 2**

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>シナリオ </p> </td> 
   <td colname="col2"> <p>history<span class="term"> 履歴 </span> をリスト変数 <span class="varname"> prop1 </span>に設定した場合、 <span class="term"> 履歴 </span> と <span class="term"> 履歴 </span> は同じ値と見なされます。 </p> <p>s.prop1="Science,History" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コード </p> </td> 
   <td colname="col2"> <p>s.prop1=s.apl(s.prop1,"history",",",2) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>結果 </p> </td> 
   <td colname="col2"> <p>s.prop1="Science,History" </p> <p> <span class="term"> 履歴 </span> は、 <span class="term"> 履歴 </span> がリストに既に存在するので追加されません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## 実装 {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

次の手順で APL プラグインを導入します。

1. カスタマーケアまたは現在の担当アドビコンサルタントに、プラグインコードをリクエストします。
1. Add call(s) to the API function as needed within the *`s_doPlugins`* function

以下はサイトでのコードの一例です。

```js
/* Plugin Config */ 
 
s.usePlugins=true 
 
function s_doPlugins(s) { 
 
/* Add calls to plugins here */ 
 
s.events=s.apl(s.events,"event1",",",1) 
 
} 
 
s.doPlugins=s_doPlugins
```

**サポートされているブラウザー**

このプラグインを使うには、ブラウザーで JavaScript バージョン 1.0 がサポートされている必要があります。

**プラグイン情報**

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> プラグイン情報 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>パラメーター </p> </td> 
   <td colname="col2"> <p>apl((L,v,d,u) </p> <p>L= ソースリスト、空白リストも可能 </p> <p> v = 付加する値 </p> <p> d = リストの区切り </p> <p> u（オプション、デフォルトは 0）固有値チェック。0=固有チェックなし。値は常に付加されます。1=大文字と小文字を区別しないチェック。値がリストにない場合にのみ付加されます。2=大文字と小文字を区別するチェック。値がリストにない場合にのみ付加されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>戻り値 </p> </td> 
   <td colname="col2"> <p>オリジナルリスト。追加の場合は付加された値も含まれます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>実例 </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1); </p> </td> 
  </tr> 
 </tbody> 
</table>

ソースリスト L は、*`L=""`* と呼ばれる iFrame を読み込みます。戻された値は、空白リストまたは 1 つの値のリストとなります。

**プラグインコード**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin Utility: apl v1.1 
 */ 
s.apl=new Function("l","v","d","u","" 
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a." 
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas" 
+"e()));}}if(!m)l=l?l+d+v:v;return l"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
  
 Not Applicable - Utility function only 
 
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
  
 s.split
```

