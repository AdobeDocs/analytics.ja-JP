---
title: getGeoCoordinates
description: 訪問者の geoLocation を追跡します。
feature: Variables
exl-id: 8620d083-7fa6-432b-891c-e24907e7c466
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 72%

---

# アドビプラグイン：getGeoCoordinates

{{plug-in}}

`getGeoCoordinates` プラグインを使用すると、訪問者のデバイスの緯度と経度を取り込むことができます。Analytics 変数で地域データを取り込む場合は、このプラグインを使用することをお勧めします。

## Web SDK 拡張機能を使用したプラグインのインストール

Adobeには、Web SDK で最もよく使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. クリック **[!UICONTROL タグ]** 左側で、目的のタグプロパティをクリックします。
1. クリック **[!UICONTROL 拡張機能]** 左側で、 **[!UICONTROL カタログ]** タブ
1. を見つけてインストールする **[!UICONTROL 共通の Web SDK プラグイン]** 拡張子。
1. クリック **[!UICONTROL データ要素]** 左側で、目的のデータ要素をクリックします。
1. 次の設定で、目的のデータ要素名を設定します。
   * 拡張：共通の Web SDK プラグイン
   * データ要素: `getGeoCoordinates`
1. 変更を保存し、データ要素に公開します。

## Web SDK の手動実装プラグインのインストール

このプラグインは、Web SDK の手動実装内での使用は、まだサポートされていません。

## Adobe Analytics拡張機能を使用したプラグインのインストール

Adobeには、Adobe Analyticsで最もよく使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getGeoCoordinates
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
/* Adobe Consulting Plugin: getGeoCoordinates v2.0  */
function getGeoCoordinates(){if(arguments&&"-v"===arguments[0])return{plugin:"getGeoCoordinates",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getGeoCoordinates="2.0");window.cookieWrite=window.cookieWrite||function(a,c,f){if("string"===typeof a){var h=window.location.hostname,b=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){b=2<b?b:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<b;)e=h.lastIndexOf(".",e-1),b--;e=0<e?h.substring(e):h}}g=e;c="undefined"!==typeof c?""+c:"";if(f||""===c)if(""===c&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(c)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===c:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var c=" "+document.cookie,b=c.indexOf(" "+a+"="),d=0>b?b:c.indexOf(";",b);return(a=0>b?"":decodeURIComponent(c.substring(b+2+a.length,0>d?c.length:d)))?a:""};var d="";b=cookieRead("s_ggc").split("|");var k={timeout:5E3,maximumAge:0},l=function(a){a=a.coords;cookieWrite("s_ggc",parseFloat(a.latitude.toFixed(4))+"|"+parseFloat(a.longitude.toFixed(4)),30);d="latitude="+parseFloat(a.latitude.toFixed(4))+" | longitude="+parseFloat(a.longitude.toFixed(4))},m=function(a){d="error retrieving geo coordinates"};1<b.length&&(d="latitude="+b[0]+" | longitude="+b[1]);navigator.geolocation&&navigator.geolocation.getCurrentPosition(l,m,k);""===d&&(d="geo coordinates not available");return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getGeoCoordinates` 関数では引数を使用しません。以下のどちらかの値を返します。

* `"geo coordinates not available"`：プラグインの実行時に利用できる地域データのないデバイスの場合。この値は、訪問の最初のヒットで一般的です。特に、訪問者が場所を追跡する際に、最初に同意する必要がある場合に使用されます。
* `"error retrieving geo coordinates"`：プラグインがデバイスの場所を取得しようとしたときにエラーが発生した場合。
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`：ここで、[LATITUDE] と [LONGITUDE] は、それぞれ緯度と経度です。

>[!NOTE]
>
> 座標値は、小数点以下 4 桁までに丸められます。例えば、`"40.438635333"` の値は `"40.4386"` に丸められ、取得される一意の値の数が制限されます。この値は、デバイスの正確な位置を 20 フィート以内に正確に示すのに十分です。

このプラグインは、必要に応じて、ヒット間の座標を保存するために「`"s_ggc"`」という名前の Cookie を使用します。

## 例

```js
// Sets eVar1 to one of the above return values depending on the visitor's device status.
s.eVar1 = getGeoCoordinates();

// Extracts latitude and longitude into their own variables called finalLatitude and finalLongitude for use in other code/applications.
var coordinates = getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}

// From there, you can determine whether a visitor is at, for example, the Statue of Liberty:
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongitude >= -74.0446 && finalLongitude <= -74.0444)
{
  var visitorAtStatueOfLiberty = true;
}
else
{
  var visitorAtStatueOfLiberty = false;
}
```

## バージョン履歴

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2015 年 5 月 25 日（PT））

* 初回リリース。
