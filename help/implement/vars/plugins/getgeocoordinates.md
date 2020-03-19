---
title: getGeoCoordinates
description: 訪問者のgeoLocationを追跡します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getGeoCoordinates

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getGeoCoordinates` ラグインを使用すると、訪問者のデバイスの緯度と経度を取り込むことができます。 Analytics変数で地域データを取り込む場合は、このプラグインの使用をお勧めします。

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
   * アクションタイプ：getGeoCoordinatesの初期化
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
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

メソッド `getGeoCoordinates` は引数を使用しません。 次のいずれかの値を返します。

* `"geo coordinates not available"`:プラグインが実行された時点で利用可能な地域データのないデバイスの場合。 この値は、訪問の最初のヒット時に共通です。特に、訪問者が場所を追跡する際に、最初に同意を示す必要がある場合に発生します。
* `"error retrieving geo coordinates"`:デバイスの場所を取得しようとすると、プラグインでエラーが発生した場合
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`:ここ [で、]LATITUDE[/] LONGITUDEは、それぞれ緯度と経度です。

> [!NOTE] 座標値は、最も近い4番目の小数点に丸められます。 例えば、の値は、取り込む `"40.438635333"` 一意の値の `"40.4386"` 数を制限するように丸められます。 この値は、デバイスの正確な位置を20フィート前後で正確に示すのに十分近い値です。

このプラグインは、必要に応じて、ヒット間の座標を保存す `"s_ggc"` るために名前付きのcookieを使用します。

## 呼び出しの例

### 例1

次のコード…

```js
s.eVar1 = s.getGeoCoordinates();
```

...eVar1を、訪問者のデバイスステータスに応じて上記の戻り値の1つに設定します。

### 例2

次のコードは、他のコード/アプリケーションで使用するために、緯度と経度をfinalLatitudeとfinalLongitudeという独自の変数に抽出します

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

ここから、例えば自由の女神など、訪問者がいるかどうかを判断できます。

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## バージョン履歴

### 1.0（2015年5月25日）

* 初回リリース。
