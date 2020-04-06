---
title: getGeoCoordinates
description: 訪問者の geoLocation を追跡します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：getGeoCoordinates

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getGeoCoordinates` プラグインを使用すると、訪問者のデバイスの緯度と経度を取り込むことができます。Analytics 変数で地域データを取り込む場合は、このプラグインを使用することをお勧めします。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getGeoCoordinates
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getGeoCoordinates` メソッドでは引数を使用しません。以下のどちらかの値を返します。

* `"geo coordinates not available"`：プラグインの実行時に利用できる地域データのないデバイスの場合。この値は、訪問の最初のヒットで一般的です。特に、訪問者が場所を追跡する際に、最初に同意する必要がある場合に使用されます。
* `"error retrieving geo coordinates"`：プラグインがデバイスの場所を取得しようとしたときにエラーが発生した場合。
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`：ここで、[LATITUDE] と [LONGITUDE] は、それぞれ緯度と経度です。

>[!NOTE] 座標値は、小数点以下 4 桁までに丸められます。例えば、`"40.438635333"` の値は `"40.4386"` に丸められ、取得される一意の値の数が制限されます。この値は、デバイスの正確な位置を 20 フィート以内に正確に示すのに十分です。

このプラグインは、必要に応じて、ヒット間の座標を保存するために「`"s_ggc"`」という名前の Cookie を使用します。

## 呼び出しの例

### 例 1

次のコードは...

```js
s.eVar1 = s.getGeoCoordinates();
```

訪問者のデバイスステータスに応じて eVar1 を上記の戻り値のいずれかに設定します。

### 例 2

次のコードは、他のコード／アプリケーションで使用するために、緯度と経度を独自の変数 finalLatitude と finalLongitude に抽出します。

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

ここから、例えば訪問者が自由の女神にいるかどうかなどを判断できます。

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## バージョン履歴

### 1.0（2015 年 5 月 26 日）

* 初回リリース。
