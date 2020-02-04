---
title: getQueryParam
description: URLのクエリ文字列パラメータの値を抽出します。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobeプラグイン：getQueryParam

> [!IMPORTANT] このプラグインは、Adobe Analyticsを使用してより多くの価値を得るために、アドビコンサルティングから提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `getQueryParam` ラグインを使用すると、URLに含まれるクエリ文字列パラメーターの値を抽出できます。 ランディングページのURLから内部および外部の両方のキャンペーンコードを抽出する場合に役立ちます。 また、検索用語や他のクエリ文字列パラメータを抽出する場合にも役立ちます。

このプラグインは、複数のクエリ文字列パラメーターを含むハッシュやURLを含む複雑なURLを解析する際に堅牢な機能を提供します。 単純なクエリ文字列パラメーターのみが必要な場合は、LaunchのURLパラメーター機能またはAppMeasurementに含まれるメソッドの使用 `Util.getQueryParam` をお勧めします。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. プラグインを使用する起動ルールに対して、次の設定を含むアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：addProductEvarの初期化
1. ルールへの変更を保存して発行します

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張」タブ [!UICONTROL に移動し] 、Adobe Analytics拡張機能の [!UICONTROL 下にある「設定] 」ボタンをクリックします。
1. 「カスタムコー [!UICONTROL ドを使用してトラッキングを設定] 」アコーディオンを展開すると、「エディターを開く  」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getQueryParam` ッドでは、次の引数を使用します。

* **`qsp`**（必須）:URL内で検索するクエリ文字列パラメーターのコンマ区切りリストです。 大文字と小文字は区別されません。
* **`de`**（オプション）:複数のクエリ文字列パラメーターが一致する場合に使用する区切り文字です。 デフォルトでは空の文字列です。
* **`url`**（オプション）:クエリ文字列パラメーターの値を抽出するカスタムURL、文字列、または変数。 初期設定はで`window.location`す。

このメソッドを呼び出すと、上記の引数とURLに応じた値が返されます。

* 一致するクエリ文字列パラメーターが見つからない場合は、空の文字列を返します。
* 一致するクエリ文字列パラメーターが見つかった場合、このメソッドはクエリ文字列パラメーター値を返します。
* 一致するクエリ文字列パラメーターが見つかったが、値が空の場合、このメソッドはを返しま `true`す。
* 一致するクエリ文字列パラメータが複数見つかった場合、このメソッドは、引数内の文字列で区切られた各パラメータ値を持つ文字列を返 `de` します。

## 呼び出しの例

### 例1

現在のURLが次の場合：

```js
http://www.abc123.com/?cid=trackingcode1
```

次のコードは、s.campaignを「trackingcode1」に設定します。

```js
s.campaign=s.getQueryParam('cid');
```

### 例2

現在のURLが次の場合：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

次のコードは、s.campaignを「trackingcode1:123456」に設定します。

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### 例3

現在のURLが次の場合：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

次のコードは、s.campaignを「trackingcode1123456」に設定します。

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### 例4

現在のURLが次の場合：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

次のコードでは、s.campaignを「123456」に設定します。

```js
s.campaign=s.getQueryParam('ecid');
```

### 例5

現在のURLが次の場合：

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

次のコードでは、s.campaignを「123456」に設定します。

```js
s.campaign=s.getQueryParam('ecid');
```

**** 注意：プラグインは、疑問符が存在しない場合、Checkのハッシュ文字のURLを疑問符に置き換えます。  URLにハッシュ文字の前に疑問符が含まれている場合、プラグインはCheckのハッシュ文字のURLをアンパサンドに置き換えます。

### 例6

現在のURLが次の場合…

```js
http://www.abc123.com/
```

...変数s.testURLが次のように設定されている場合、

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

次のコードは、s.campaignをまったく設定しません。

```js
s.campaign=s.getQueryParam('cid');
```

ただし、次のコードでは、s.campaignを「trackingcode1」に設定します。

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**** 注意：3つ目のパラメーターは、

次のコードは、s.eVar2を&quot;123456|trackingcode1|true|300&quot;に設定します。

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* 123456の値は、s.testURL変数のecidパラメーターから取得されます。
* trackingcode1の値は、s.testURL変数のcidパラメーターから取得されます
* trueの値は、s.testURL変数内のハッシュ文字の後の場所パラメーターの存在（値以外）から取得されます

300の値は、s.testURL変数のposパラメーターの値から取得されます。

## バージョン履歴

### 3.3（2019年9月24日）

* 不要なロジックを迂回してコードサイズを縮小

### 3.2（2018年5月16日）

* 関数内 `findParameterValue` に移動 `getParameterValue` および関数を移動し `getQueryParam` ました

### 3.1（2018年5月10日）

* 値のないクエリ文字列パラメーターの取得に関する問題を修正しました

### 3.0（2018年4月17日）

* ポイントリリース（再コンパイル、コードサイズが小さい）。
* ヘルパー関数の名前を読みやす `findParameterValue` くするた `getParameterValue` めに、およびに変更しました。
* URLハッシュに含まれるパラメーターを見つけるための引数を追加する必要がなくなりました。

### 2.5（2016年1月9日）

* HコードとAppMeasurementの両方と互換性があります(AppMeasurementと共に `s.pt` 必要です)。

### 2.4

* パラメーター `h` が追加され、ハッシュ文字(`#`)の後に見つかったクエリ文字列パラメーターをコードで検索できるようになりました。

### 2.3

* トラッキングコードの後にハッシュが存在する場合にのみプラグインが機能するという回帰問題を修正。

### 2.2

* 戻り値からハッシュ文字（およびその後のすべて）を削除します。

### 2.1

* H.10コードと互換
