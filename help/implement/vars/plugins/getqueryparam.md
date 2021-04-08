---
title: getQueryParam
description: URL のクエリー文字列パラメーターの値を抽出します。
translation-type: ht
source-git-commit: 03c3a954c40d17f11f4f80ee3a378fd43948cc5c
workflow-type: ht
source-wordcount: '896'
ht-degree: 100%

---


# アドビプラグイン：getQueryParam

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getQueryParam` プラグインを使用すると、URL に含まれるクエリー文字列パラメーターの値を抽出できます。これは、ランディングページの URL から内部および外部の両方のキャンペーンコードを抽出する場合に役立ちます。また、検索用語や他のクエリー文字列パラメーターを抽出する場合にも役立ちます。

このプラグインは、複数のクエリー文字列パラメーターを含むハッシュや URL を含む複雑な URL を解析する際に堅牢な機能を提供します。単純なクエリー文字列パラメーターのみが必要な場合は、Launch の URL パラメーター機能または AppMeasurement に含まれる [`Util.getQueryParam()`](../functions/util-getqueryparam.md) メソッドの使用をお勧めします。

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
   * Action Type：Initialize getQueryParam
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「[!UICONTROL 設定]」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0 */
function getQueryParam(b,c,d){function h(b,a){a=a.split("?").join("&");a=a.split("#").join("&");var c=a.indexOf("&");if(b&&(-1<c||a.indexOf("=")>c)){c=a.substring(c+1);c=c.split("&");for(var d=0,k=c.length;d<k;d++){var f=c[d].split("="),e=f[1];if(f[0].toLowerCase()===b.toLowerCase())return decodeURIComponent(e||!0)}}}if("-v"===b)return{plugin:"getQueryParam",version:"4.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getQueryParam="4.0");if(b){c=c||"";d=(d||"undefined"!==typeof a&&a.pageURL||location.href)+"";(4<c.length||-1<c.indexOf("="))&&d&&4>d.length&&(a=c,c=d,d=a);a="";for(var g=b.split(","),l=g.length,e=0;e<l;e++)b=h(g[e],d),"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,a+=a?c+b:b):a=""===a?b:a+(c+b);return a}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getQueryParam` メソッドでは、次の引数を使用します。

* **`qsp`**（必須）：URL 内で検索するクエリー文字列パラメーターのコンマ区切りリストです。大文字と小文字は区別されません。
* **`de`**（オプション）：複数のクエリー文字列パラメーターが一致する場合に使用する区切り文字です。デフォルトでは空の文字列です。
* **`url`**（オプション）：クエリー文字列パラメーターの値を抽出するカスタム URL、文字列、または変数です。デフォルト値は `window.location` です。

このメソッドを呼び出すと、上記の引数と URL に応じた値が返されます。

* 一致するクエリー文字列パラメーターが見つからない場合は、空の文字列を返します。
* 一致するクエリー文字列パラメーターが見つかった場合、このメソッドはクエリー文字列パラメーター値を返します。
* 一致するクエリー文字列パラメーターが見つかったが値が空の場合、このメソッドは `true` を返します。
* 一致するクエリー文字列パラメーターが複数見つかった場合、このメソッドは `de` 引数内の文字列で区切られた各パラメーター値を持つ文字列を返します。

## 呼び出しの例

### 例 1

現在の URL が次の場合：

```js
http://www.abc123.com/?cid=trackingcode1
```

次のコードは、s.campaign を「trackingcode1」に設定します。

```js
s.campaign=s.getQueryParam('cid');
```

### 例 2

現在の URL が次の場合：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

次のコードは、s.campaign を「trackingcode1:123456」に設定します。

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### 例 3

現在の URL が次の場合：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

次のコードは、s.campaign を「trackingcode1123456」に設定します。

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### 例 4

現在の URL が次の場合：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

次のコードでは、s.campaign を「123456」に設定します。

```js
s.campaign=s.getQueryParam('ecid');
```

### 例 5

現在の URL が次の場合：

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

次のコードでは、s.campaign を「123456」に設定します。

```js
s.campaign=s.getQueryParam('ecid');
```

**注意：**&#x200B;疑問符が存在しない場合、プラグインは、Check のハッシュ文字の URL を疑問符に置き換えます。URL にハッシュ文字の前に疑問符が含まれている場合、プラグインは Check のハッシュ文字の URL をアンパサンドに置き換えます。

### 例 6

現在の URL が次で、

```js
http://www.abc123.com/
```

変数 s.testURL が次のように設定されている場合、

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

次のコードは、s.campaign をまったく設定しません。

```js
s.campaign=s.getQueryParam('cid');
```

ただし、次のコードでは、s.campaign を「trackingcode1」に設定します。

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**注意：** 3 つ目のパラメーターは、コードでクエリー文字列パラメーターを検索するために使用する任意の文字列／変数を指定できます。

次のコードは、s.eVar2 を「123456|trackingcode1|true|300」に設定します。

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* 123456 の値は、s.testURL 変数の ecid パラメーターから取得されます。
* trackingcode1 の値は、s.testURL 変数の cid パラメーターから取得されます。
* true の値は、s.testURL 変数内のハッシュ文字の後の場所パラメーターの存在（値以外）から取得されます。

300 の値は、s.testURL 変数の pos パラメーターの値から取得されます。

## バージョン履歴

### 4.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。
* プラグインへの依存関係を削除しました `pt`。

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
