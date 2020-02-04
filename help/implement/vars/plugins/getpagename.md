---
title: getPageName
description: 現在のWebサイトのパスから読みやすいpageNameを作成します。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobeプラグイン：getPageName

> [!IMPORTANT] このプラグインは、Adobe Analyticsを使用してより多くの価値を得るために、アドビコンサルティングから提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `getPageName` ラグインは、読みやすく、わかりやすい形式の現在のURLを作成します。 レポートで設定しやすく理解しやすい値が必要な場合は、こ `pageName` のプラグインを使用することをお勧めします。 このプラグインは、データレイヤーを介してなど、変数の命名構造が既に `pageName` ある場合は不要です。 この変数は、変数を設定する別のソリューションがない場合に最適で `pageName` す。

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

## AppMeasurementを使用したプラグインのインストール

Analyticsトラッキングオブジェクトをインスタンス化した後（を使用して）、AppMeasurementファイルの任意の場所に次のコードをコピーして貼り付 `s_gi`けます。 コードのコメントとバージョン番号を実装に保持しておくと、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getPageName` ッドでは、次の引数を使用します。

* **`si`**（オプション、文字列）:サイトのIDを表す文字列の先頭に挿入されるID。 この値は、数値IDまたはわかりやすい名前にすることができます。 設定しない場合は、デフォルトで現在のドメインが使用されます。
* **`qv`**（オプション、文字列）:URL内にある場合に文字列に追加されるクエリ文字列パラメーターのコンマ区切りリスト
* **`hv`**（オプション、文字列）:URLハッシュに含まれるパラメーターのコンマ区切りリスト。URL内に含まれる場合は文字列に追加されます
* **`de`**（オプション、文字列）:文字列の個々の部分を分割する区切り文字です。 デフォルトはパイプ(`|`)です。

このメソッドは、わかりやすい形式のURLを含む文字列を返します。 この文字列は通常変数に割り当て `pageName` られますが、他の変数でも使用できます。

## 呼び出しの例

### 例1

現在のURLが

```js
https://mail.google.com/mail/u/0/#inbox
```

...次のコードが実行されます。

```js
s.pageName = getPageName()
```

...s.pageNameの最後の値は次のようになります。

```js
s.pageName = "mail.google.com|mail|u|0";
```

### 例2

現在のURLが

```js
https://mail.google.com/mail/u/0/#inbox
```

...次のコードが実行されます。

```js
s.pageName = getPageName("gmail")
```

...s.pageNameの最後の値は次のようになります。

```js
s.pageName = "gmail|mail|u|0";
```

### 例3

現在のURLが

```js
https://www.google.com/
```

...次のコードが実行されます。

```js
s.pageName = getPageName()
```

...s.pageNameの最後の値は次のようになります。

```js
s.pageName = "www.google.com|home"
```

**注意**:パスを含まないURLでコードを実行する場合、常に戻り値の末尾に「home」の値が追加されます

### 例4

現在のURLが

```js
https://www.google.com/
```

...次のコードが実行されます。

```js
s.pageName = getPageName("google","","","|")
```

...s.pageNameの最後の値は次のようになります。

```js
s.pageName = "google|home"
```

### 例5

現在のURLが

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...次のコードが実行されます。

```js
s.pageName = getPageName()
```

...s.pageNameの最後の値は次のようになります。

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

ただし、代わりに次のコードを実行する場合は、

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...s.pageNameの最後の値は次のようになります。

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## 以前のバージョンからのアップグレード

getPageNameプラグインのバージョン4.0以降は、実行するAdobe AnalyticsのAppMeasurementオブジェクト（「s」オブジェクト）の存在に依存しません。  このバージョンにアップグレードする場合は、「s」オブジェクトのインスタンスを呼び出しから削除して、プラグインを呼び出すコードを必ず変更してください。
例えば、次のように変更します。

```js
s.pageName = s.getPageName();
```

...を次のように指定します。

```js
s.pageName = getPageName();
```

## バージョン履歴

### 4.1（2019年9月18日）

* デフォルトの区切り文字の値を（コロン+スペースから）パイプ文字に変更しました。

### 4.0（2018年5月23日）

* プラグインの再分析/書き換えの完了
