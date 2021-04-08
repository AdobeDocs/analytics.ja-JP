---
title: manageVars
description: 一度に複数の Analytics 変数の値を変更します。
translation-type: ht
source-git-commit: 93a2dc1b265c92468722ebc2e3656db55d63547c
workflow-type: ht
source-wordcount: '697'
ht-degree: 100%

---


# アドビプラグイン：manageVars

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`manageVars` プラグインを使用すると、複数の Analytics 変数の値を一度に操作できます。また、値を小文字に設定したり、複数の変数値から不要な文字を同時に削除したりすることもできます。複数の変数の値を一度にクリーンアップする場合は、このプラグインを使用することをお勧めします。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize manageVars
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「[!UICONTROL 設定]」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`manageVars` メソッドでは、次の引数を使用します。

* **`cb`**（必須、文字列）：プラグインが Analytics 変数の操作に使用するコールバック関数の名前です。`cleanStr` のようなアドビの関数または独自のカスタム関数を使用できます。
* **`l`**（オプション、文字列）：操作する Analytics 変数のコンマ区切りリストです。未設定の場合はデフォルトですべての Adobe Analytics 変数に設定され、次の変数が含まれます。
   * `pageName`
   * `purchaseID`
   * `channel`
   * `server`
   * `pageType`
   * `campaign`
   * `state`
   * `zip`
   * `events`
   * `products`
   * `transactionID`
   * すべての prop
   * すべての eVar
   * すべての階層変数
   * すべてのリスト変数
   * すべてのコンテキストデータ変数
* **`Il`**（オプション、ブール値）：`l` 引数で宣言された変数のリストを含める代わりに&#x200B;*除外*&#x200B;する場合には `false` に設定します。デフォルト値は `true` です。

このメソッドを呼び出すと、何も返されません。代わりに、目的のコールバック関数に基づいて Analytics 変数の値を変更します。

## 呼び出しの例

### 例 1

次のコードは...

```js
s.manageVars("lowerCaseVars");
```

上記のすべての変数の値を小文字に変換します。これに対する唯一の例外は、一部のイベント変数です。イベント変数（scAdd、scCheckout など）では大文字と小文字が区別され、大文字を小文字にすることはできません。

### 例 2

次のコードは...

```js
s.manageVars("lowerCaseVars", "events", false);
```

基本的に、最初の例とまったく同じ結果が得られます。これは、イベント変数がデフォルトで小文字化されないためです。

### 例 3

次のコードは...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

eVar1、eVar2、eVar3、list2 の値のみを変更（小文字に）します。

### 例 4

次のコードは...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

上記の eVar1、eVar2、eVar3、list2 を除くすべての変数の値を変更（小文字に）します。

### 例 5

次のコードは...

```js
s.manageVars("cleanStr");
```

イベント変数を含む、上記のすべての変数の値を変更します。具体的には、cleanStr コールバック関数は各変数の値に対して次の処理をおこないます。

* HTML エンコーディングを削除します。
* 値の先頭と末尾にある空白を削除します。
* 左右の曲がった一重引用符（「’」）をまっすぐな一重引用符（「&#39;」）に置き換えます。
* タブ文字、改行文字、キャリッジリターン文字をスペースに置き換えます。
* すべての 2 つ以上のスペースを1 つのスペースに置き換えます。

## バージョン履歴

### 3.0 （2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 2.1（2019 年 1 月 14 日（PT））

* Internet Explorer 11 ブラウザーのバグ修正。
* `s.cleanStr` が通常の `cleanStr` 関数を使用するように変更しました。

### 2.0（2018 年 5 月 7 日（PT））

* ポイントリリース（プラグインの完全な再分析と書き換えを含む）
* `cleanStr` コールバック関数を追加しました。
