---
title: getPageName
description: 現在の Web サイトのパスから読みやすい pageName を作成します。
feature: Appmeasurement Implementation
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 75%

---

# アドビプラグイン：getPageName

{{plug-in}}

`getPageName` プラグインは、読みやすく、わかりやすい形式の現在の URL を作成します。レポートで設定しやすく理解しやすい [`pageName`](../page-vars/pagename.md) 値が必要な場合は、このプラグインを使用することをお勧めします。このプラグインは、データレイヤーを介してなど、`pageName` 変数の命名構造が既にある場合は不要です。この変数は、`pageName` 変数を設定する別のソリューションがない場合に最適です。

## Web SDK拡張機能を使用したプラグインのインストール

Adobeには、web SDKで最も一般的に使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 左側の **[!UICONTROL タグ]** をクリックしてから、目的のタグプロパティをクリックします。
1. 左側の **[!UICONTROL 拡張機能]** をクリックしてから、「**[!UICONTROL カタログ]**」タブをクリックします
1. **[!UICONTROL Common Web SDK Plugins]** 拡張機能を見つけてインストールします。
1. 左側の **[!UICONTROL データ要素]** をクリックしてから、目的のデータ要素をクリックします。
1. 次の設定で、目的のデータ要素名を設定します。
   * 拡張機能：Common Web SDK Plugins
   * データ要素：`getPageName`
1. 必要なパラメーターを右側に設定します。
1. 変更を保存してデータ要素に公開します。

## Web SDKを手動で実装するプラグインのインストール

このプラグインは、web SDKの手動実装内での使用はまだサポートされていません。

## Adobe Analytics拡張機能を使用してプラグインをインストールします

Adobeには、Adobe Analyticsで最も一般的に使用されるプラグインを使用できる拡張機能があります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getPageName
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターを使用したプラグインのインストール

Common Analytics Plugins プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングを行う際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getPageName` 関数は次の引数を使用します。

* **`si`**（オプション、文字列）：サイトの ID を表す文字列の先頭に挿入される ID。この値は、数値 ID またはわかりやすい名前にすることができます。設定しない場合は、デフォルトで現在のドメインが使用されます。
* **`qv`**（オプション、文字列）：URL 内にある場合に文字列に追加されるクエリ文字列パラメーターのコンマ区切りリストです。
* **`hv`**（オプション、文字列）：URL ハッシュに含まれるパラメーターのコンマ区切りリストです。URL 内に含まれる場合は文字列に追加されます。
* **`de`**（オプション、文字列）：文字列の個々の部分を分割する区切り文字です。デフォルトはパイプ（`|`）です。

この関数は、わかりやすい形式の URL を含む文字列を返します。この文字列は通常 `pageName` 変数に割り当てられますが、他の変数でも使用できます。

## 例

```js
// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "mail.example.com|mail|u|0".
s.pageName = getPageName();

// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "example|mail|u|0".
s.pageName = getPageName("example");

// Given the URL https://www.example.com/, sets the page variable to "www.example.com|home".
// When the code runs on a URL that does not contain a path, it always adds the value of "home" to the end of the return value.
s.pageName = getPageName();

// Given the URL https://www.example.com/, sets the page variable to "example|home".
s.pageName = getPageName("example","","","|");

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "www.example.com|en|booking|room-booking.html".
s.pageName = getPageName();

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "example: en: booking: room-booking.html: cid=1235: arrive=05-26: numGuests=2"
s.pageName = getPageName("example","cid","arrive,numGuests",": ");
```

## 以前のバージョンからのアップグレード

`getPageName` プラグインのバージョン 4.0 以降は、Adobe Analytics の AppMeasurement オブジェクト（`s` オブジェクト）の存在に依存しません。このバージョンにアップグレードする場合は、呼び出しから `s` オブジェクトの任意のインスタンスを削除し、プラグインを呼び出すコードを変更してください。例えば、`s.getPageName();` を `getPageName();` に変更します。

## バージョン履歴

### 4.2（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 4.1（2019 年 9 月 17 日（PT））

* デフォルトの区切り文字の値を（コロン+スペースから）パイプ文字に変更しました。

### 4.0（2018 年 5 月 22 日（PT））

* プラグインの完全な再分析と書き換え
