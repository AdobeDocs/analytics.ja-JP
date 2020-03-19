---
title: manageVars
description: 一度に複数のAnalytics変数の値を変更します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：manageVars

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `manageVars` ラグインを使用すると、複数のAnalytics変数の値を一度に操作できます。 また、値を小文字に設定したり、複数の変数値から不要な文字を同時に削除したりすることもできます。 複数の変数の値を一度にクリーンアップする場合は、このプラグインの使用をお勧めします。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最もよく使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、ボタンをクリックしま [!UICONTROL Catalog] す。
1. 拡張機能のインストールと公 [!UICONTROL Common Analytics Plugins] 開
1. まだ設定していない場合は、「Initialize Plug-ins」というラベルの付いたルールを次の設定で作成します。
   * 条件：なし
   * イベント：コア — ライブラリ読み込み済み（ページの上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：manageVarsの初期化
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、Adobe Analytics拡張機能の下 [!UICONTROL Configure] にあるボタンをクリックします。
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

次のコードを、Analyticsトラッキングオブジェクトのインスタンス化（を使用）後に、AppMeasurementファイルの任意の場所にコピーして貼り付 [`s_gi`](../functions/s-gi.md)けます。 導入時にコードのコメントとバージョン番号を保持すると、アドビは潜在的な問題のトラブルシューティングに役立ちます。

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

このメソ `manageVars` ッドでは、次の引数を使用します。

* **`cb`** （必須、文字列）:プラグインがAnalytics変数の操作に使用するコールバック関数の名前。 アドビの機能は、と同様に、または独自のカ `cleanStr` スタム機能と同様に使用できます。
* **`l`** （オプション、文字列）:操作するAnalytics変数のコンマ区切りのリストです。 設定しない場合は、次を含むすべてのAdobe Analytics変数がデフォルトで使用されます。
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
   * すべてのprop
   * すべてのeVar
   * すべての階層変数
   * すべてのリスト変数
   * すべてのコンテキストデータ変数
* **`Il`** （オプション、ブール値）:引数で宣言 `false` された変数を含め *るので* 、変数のリストを除外する場合に `l` 設定します。 初期設定はで `true`す。

このメソッドを呼び出すと、何も返されません。 代わりに、目的のコールバック関数に基づいてAnalytics変数の値を変更します。

## 呼び出しの例

### 例1

次のコード…

```js
s.manageVars("lowerCaseVars");
```

...上記のすべての変数の値を小文字で表記した値に変更します。  これに対する唯一の例外は、イベント変数で、一部のイベント（scAdd、scCheckoutなど）と同様には大文字と小文字が区別され、小文字は使用しないでください。

### 例2

次のコード…

```js
s.manageVars("lowerCaseVars", "events", false);
```

...基本的には、イベント変数がデフォルトで小文字化されていないので、最初の例とまったく同じ結果になります。

### 例3

次のコード…

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...は、eVar1、eVar2、eVar3、list2の値のみが変更（小文字のみ）されます。

### 例4

次のコード…

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...は、eVar1、eVar2、eVar3およびlist2を除く、上記のすべての変数の値（小文字など）を変更します。

### 例5

次のコード…

```js
s.manageVars("cleanStr");
```

...イベント変数を含む、上記のすべての変数の値を変更します。  具体的には、cleanStrコールバック関数は、各変数の値に対して次の処理を行います。

* HTMLエンコーディングを削除
* 値の先頭と末尾にある空白を削除します。
* 左または右の一重引用符を置換します(例：’)を一重引用符(&#39;)で囲む
* タブ文字、改行文字および復帰文字をスペースに置き換えます。
* 全ての倍精度（または三重など）を置き換えます。スペースとスペース

## バージョン履歴

### 2.1（2019年1月14日）

* Internet Explorer 11ブラウザーのバグ修正。
* の変更点で `s.cleanStr`す。現在は、通常の関数を使用し `cleanStr` ます。

### 2.0（2018年5月7日）

* ポイントリリース（プラグインの完全な再分析/書き換えを含む）
* コールバック `cleanStr` 関数の追加
