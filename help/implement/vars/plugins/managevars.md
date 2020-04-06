---
title: manageVars
description: 一度に複数の Analytics 変数の値を変更します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：manageVars

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`manageVars` プラグインを使用すると、複数の Analytics 変数の値を一度に操作できます。また、値を小文字に設定したり、複数の変数値から不要な文字を同時に削除したりすることもできます。複数の変数の値を一度にクリーンアップする場合は、このプラグインを使用することをお勧めします。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
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
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
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

### 2.1（2019 年 1 月 15 日）

* Internet Explorer 11 ブラウザーのバグ修正。
* `s.cleanStr` が通常の `cleanStr` 関数を使用するように変更しました。

### 2.0（2018 年 5 月 8 日）

* ポイントリリース（プラグインの完全な再分析と書き換えを含む）
* `cleanStr` コールバック関数を追加しました。
