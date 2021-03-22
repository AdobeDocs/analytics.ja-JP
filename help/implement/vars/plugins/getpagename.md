---
title: getPageName
description: 現在の Web サイトのパスから読みやすい pageName を作成します。
translation-type: tm+mt
source-git-commit: 063da38c105072944a46ec0ab31930623b7974c8
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 99%

---


# アドビプラグイン：getPageName

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getPageName` プラグインは、読みやすく、わかりやすい形式の現在の URL を作成します。レポートで設定しやすく理解しやすい [`pageName`](../page-vars/pagename.md) 値が必要な場合は、このプラグインを使用することをお勧めします。このプラグインは、データレイヤーを介してなど、`pageName` 変数の命名構造が既にある場合は不要です。この変数は、`pageName` 変数を設定する別のソリューションがない場合に最適です。

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
   * Action Type：Initialize getPageName
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
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getPageName` メソッドでは、次の引数を使用します。

* **`si`**（オプション、文字列）：サイトの ID を表す文字列の先頭に挿入される ID。この値は、数値 ID またはわかりやすい名前にすることができます。設定しない場合は、デフォルトで現在のドメインが使用されます。
* **`qv`**（オプション、文字列）：URL 内にある場合に文字列に追加されるクエリー文字列パラメーターのコンマ区切りリストです。
* **`hv`**（オプション、文字列）：URL ハッシュに含まれるパラメーターのコンマ区切りリストです。URL 内に含まれる場合は文字列に追加されます。
* **`de`**（オプション、文字列）：文字列の個々の部分を分割する区切り文字です。デフォルトはパイプ（`|`）です。

このメソッドは、わかりやすい形式の URL を含む文字列を返します。この文字列は通常 `pageName` 変数に割り当てられますが、他の変数でも使用できます。

## 呼び出しの例

### 例 1

現在の URL が以下の場合、

```js
https://mail.google.com/mail/u/0/#inbox
```

次のコードが実行された場合、

```js
s.pageName = getPageName()
```

s.pageName の最終値は次のようになります。

```js
s.pageName = "mail.google.com|mail|u|0";
```

### 例 2

現在の URL が以下の場合、

```js
https://mail.google.com/mail/u/0/#inbox
```

次のコードが実行された場合、

```js
s.pageName = getPageName("gmail")
```

s.pageName の最終値は次のようになります。

```js
s.pageName = "gmail|mail|u|0";
```

### 例 3

現在の URL が以下の場合、

```js
https://www.google.com/
```

次のコードが実行された場合、

```js
s.pageName = getPageName()
```

s.pageName の最終値は次のようになります。

```js
s.pageName = "www.google.com|home"
```

**注意**：パスを含まない URL でコードを実行する場合、常に戻り値の末尾に「home」の値が追加されます

### 例 4

現在の URL が以下の場合、

```js
https://www.google.com/
```

次のコードが実行された場合、

```js
s.pageName = getPageName("google","","","|")
```

s.pageName の最終値は次のようになります。

```js
s.pageName = "google|home"
```

### 例 5

現在の URL が以下の場合、

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

次のコードが実行された場合、

```js
s.pageName = getPageName()
```

s.pageName の最終値は次のようになります。

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

ただし、代わりに次のコードを実行する場合は、

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

s.pageName の最終値は次のようになります。

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## 以前のバージョンからのアップグレード

getPageName プラグインのバージョン 4.0 以降は、実行する Adobe Analytics の AppMeasurement オブジェクト（「s」オブジェクト）の存在に依存しません。このバージョンにアップグレードする場合は、「s」オブジェクトのインスタンスをプラグインを呼び出すコードから必ず削除してください。
例えば、次のコードは

```js
s.pageName = s.getPageName();
```

次のように変更します。

```js
s.pageName = getPageName();
```

## バージョン履歴

### 4.2（2021年3月19日）

* コンテキストデータとしてバージョン番号を追加しました。

### 4.1（2019 年 9 月 18 日）

* デフォルトの区切り文字の値を（コロン+スペースから）パイプ文字に変更しました。

### 4.0（2018 年 5 月 23 日）

* プラグインの完全な再分析と書き換え
