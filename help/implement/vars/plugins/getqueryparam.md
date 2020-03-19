---
title: getQueryParam
description: URLのクエリ文字列パラメータの値を抽出します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getQueryParam

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getQueryParam` ラグインを使用すると、URLに含まれるクエリ文字列パラメータの値を抽出できます。 ランディングページのURLから、内部と外部の両方のキャンペーンコードを抽出する場合に役立ちます。 また、検索用語や他のクエリ文字列パラメータを抽出する場合にも役立ちます。

このプラグインは、複数のクエリ文字列パラメーターを含むハッシュやURLを含む、複雑なURLを解析する際の堅牢な機能を提供します。 単純なクエリ文字列パラメーターのみが必要な場合は、LaunchのURLパラメーター機能またはAppMeasurementに含まれるメソッドの使用 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) をお勧めします。

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
   * アクションタイプ：getQueryParamの初期化
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、Adobe Analytics拡張機能の下 [!UICONTROL Configure] にあるボタンをクリックします。
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
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

* **`qsp`** （必須）:URL内で検索するクエリ文字列パラメーターのコンマ区切りリストです。 大文字と小文字は区別されません。
* **`de`** （オプション）:複数のクエリ文字列パラメーターが一致する場合に使用する区切り文字です。 デフォルトは空の文字列です。
* **`url`** （オプション）:クエリ文字列パラメータ値を抽出するカスタムURL、文字列、または変数。 初期設定はで `window.location`す。

このメソッドを呼び出すと、上記の引数とURLに応じた値が返されます。

* 一致するクエリ文字列パラメーターが見つからない場合は、空の文字列を返します。
* 一致するクエリ文字列パラメーターが見つかった場合、このメソッドはクエリ文字列パラメーター値を返します。
* 一致するクエリ文字列パラメーターが見つかったが、値が空の場合、このメソッドはを返しま `true`す。
* 一致するクエリ文字列パラメータが複数見つかった場合、このメソッドは、各パラメータ値を引数内の文字列で区切った文字列を返 `de` します。

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

次のコードでは、s.campaignが「123456」に設定されます。

```js
s.campaign=s.getQueryParam('ecid');
```

### 例5

現在のURLが次の場合：

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

次のコードでは、s.campaignが「123456」に設定されます。

```js
s.campaign=s.getQueryParam('ecid');
```

**注意：** プラグインは、Checkのハッシュ文字のURLを、疑問符が存在しない場合は疑問符に置き換えます。  URLにハッシュ文字の前に疑問符が含まれている場合、プラグインは、Checkのハッシュ文字のURLをアンパサンド(&amp;)に置き換えます。

### 例6

現在のURLが次の場合…

```js
http://www.abc123.com/
```

...変数s.testURLが次のように設定されている場合、

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

次のコードでは、s.campaignがまったく設定されません。

```js
s.campaign=s.getQueryParam('cid');
```

ただし、次のコードでは、s.campaignを「trackingcode1」に設定します。

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**注意：** 3つ目のパラメーターは、コードが

次のコードは、s.eVar2を&quot;123456|trackingcode1|true|300&quot;に設定します。

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* 123456の値は、s.testURL変数のecidパラメーターから取得されます。
* trackingcode1の値は、s.testURL変数のcidパラメーターから取得されます
* trueの値は、s.testURL変数内のハッシュ文字の後の場所パラメーターの存在（値以外）から取得されます

300という値は、s.testURL変数のposパラメーターの値から取得されます。

## バージョン履歴

### 3.3（2019年9月24日）

* 不要なロジックをバイパスしてコードサイズを縮小

### 3.2（2018年5月16日）

* 関数内 `findParameterValue` に移動 `getParameterValue` および関数を移 `getQueryParam` 動

### 3.1（2018年5月10日）

* 値のないクエリ文字列パラメーターの取り込みに関する問題を修正しました。

### 3.0（2018年4月17日）

* ポイントリリース（再コンパイルされ、コードサイズが小さくなりました）。
* ヘルパー関数の名前を読みやす `findParameterValue` くするた `getParameterValue` めに、およびに変更しました。
* URLハッシュに含まれるパラメーターを検索するための引数を追加する必要がなくなりました。

### 2.5（2016年1月9日）

* HコードとAppMeasurementの両方と互換性があります(AppMeasurement `s.pt` との連携が必要)。

### 2.4

* ハッシュ( `h``#`)文字の後にあるクエリ文字列パラメータをコードで検索できるように、パラメータを追加しました。

### 2.3

* トラッキングコードの後にハッシュが存在する場合にのみプラグインが機能する問題を修正しました。

### 2.2

* 戻り値からハッシュ文字（およびその後のすべて）を削除します。

### 2.1

* H.10コードとの互換性
