---
title: getQueryParam
description: URL のクエリー文字列パラメーターの値を抽出します。
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 92%

---

# アドビプラグイン：getQueryParam

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getQueryParam` プラグインを使用すると、URL に含まれるクエリー文字列パラメーターの値を抽出できます。これは、ランディングページの URL から内部および外部の両方のキャンペーンコードを抽出する場合に役立ちます。また、検索用語や他のクエリー文字列パラメーターを抽出する場合にも役立ちます。

このプラグインは、複数のクエリー文字列パラメーターを含むハッシュや URL を含む複雑な URL を解析する際に堅牢な機能を提供します。単純なクエリー文字列パラメーターのみが必要な場合は、Web SDK またはAdobe Analytics拡張機能を使用するか、 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) メソッドが AppMeasurement に含まれています。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getQueryParam
1. Save and publish the changes to the rule.-->

## カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getQueryParam` 関数は次の引数を使用します。

* **`qsp`**（必須）：URL 内で検索するクエリー文字列パラメーターのコンマ区切りリストです。大文字と小文字は区別されません。
* **`de`**（オプション）：複数のクエリー文字列パラメーターが一致する場合に使用する区切り文字です。デフォルトでは空の文字列です。
* **`url`**（オプション）：クエリー文字列パラメーターの値を抽出するカスタム URL、文字列、または変数です。デフォルト値は `window.location` です。

この関数を呼び出すと、上記の引数と URL に応じた値が返されます。

* 一致するクエリ文字列パラメーターが見つからない場合は、空の文字列を返します。
* 一致するクエリ文字列パラメーターが見つかった場合、この関数はクエリ文字列パラメーター値を返します。
* 一致するクエリ文字列パラメーターが見つかったが値が空の場合、この関数は `true` を返します。
* 一致するクエリ文字列パラメーターが複数見つかった場合、この関数は `de` 引数内の文字列で区切られた各パラメーター値を持つ文字列を返します。

## 例

```js
// Given the URL https://example.com/?cid=trackingcode
// Sets the campaign variable to "trackingcode"
s.campaign = getQueryParam('cid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode:123"
s.campaign = getQueryParam('cid,ecid',':');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode123"
s.campaign = getQueryParam('cid,ecid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123#location
// Sets the campaign variable to "123"
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com/#location&cid=trackingcode&ecid=123
// Sets the campaign variable to "123"
// The plug-in replaces the URL's hash character with a question mark if a question mark doesn't exist.
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com
// Does not set the campaign variable to a value.
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid');

// Given the URL https://example.com
// Sets the campaign variable to "trackingcode"
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid','',s.pageURL);

// Given the URL https://example.com
// Sets eVar2 to "123|trackingcode|true|300"
s.eVar1 = "https://example.com/?cid=trackingcode&ecid=123#location&pos=300";
s.eVar2 = getQueryParam('ecid,cid,location,pos','|',s.eVar1);
```

## バージョン履歴

### 4.0.1（2021 年 3 月 26 日（PT））

* クエリーパラメーターがクエリー文字列に存在しない場合、「」の代わりに undefined が返される問題を更新しました。

### 4.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。
* pt プラグインへの依存関係を削除しました。

### 3.3（2019 年 9 月 24 日（PT））

* 不要なロジックを迂回してコードサイズを縮小しました。

### 3.2（2018 年 5 月 15 日（PT））

* `findParameterValue` 関数および `getParameterValue` 関数を `getQueryParam` 関数内に移動しました。

### 3.1（2018 年 5 月 10 日（PT））

* 値のないクエリー文字列パラメーターの取得に関する問題を修正しました。

### 3.0（2018 年 4 月 16 日（PT））

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* ヘルパー関数の名前を読みやすくするために、`findParameterValue` および `getParameterValue` に変更しました。
* URL ハッシュに含まれるパラメーターを見つけるための引数を追加する必要がなくなりました。

### 2.5（2016 年 1 月 8 日（PT））

* H コードと AppMeasurement の両方と互換性があります（AppMeasurement と `s.pt` が必要です）。

### 2.4

* `h` パラメーターを追加し、ハッシュ文字（`#`）の後に見つかったクエリー文字列パラメーターをコードで検索できるようになりました。

### 2.3

* トラッキングコードの後にハッシュが存在する場合にのみプラグインが機能するという回帰問題を修正しました。

### 2.2

* 戻り値からハッシュ文字（およびその後のすべて）を削除するようになりました。

### 2.1

* H.10 コードと互換
