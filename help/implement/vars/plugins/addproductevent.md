---
title: addProductEvent
description: カスタムイベントを製品およびイベント変数に追加します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe プラグイン：addProductEvent

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`addProductEvent` プラグインは、数値イベントまたは通貨イベントを [`products`](../page-vars/products.md) 変数に追加します。製品文字列の形式を気にせずに数値イベントや通貨イベントを `products` 変数に追加する場合は、このプラグインを使用することをお勧めします。このプラグインは、`products` 変数で数値イベントや通貨イベントを使用しない場合は不要です。

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
   * Action Type：Initialize addProductEvent
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
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`addProductEvent` メソッドでは、次の引数を使用します。

* **`en`**（必須、文字列）：`products` 変数の最後のエントリに追加するイベント。`products` 変数が空の場合、イベント（およびその値）が添付された「空白」の製品エントリが作成されます。
* **`ev`**（必須、文字列）：`en` 引数内の数値イベントまたは通貨イベントに割り当てられる値。未設定の場合のデフォルト値は `1` です。
* **`ap`**（オプション、ブール値）：現在、products 変数に複数の製品エントリが含まれている場合、値が `true`（または `1`）の場合、すべての製品エントリにイベントが追加されます。未設定の場合のデフォルト値は `false` です。

`addProductEvent` は何も返しません。代わりに、イベントとその値が `products` 変数に追加されます。また、このプラグインは [`events`](../page-vars/events/events-overview.md) 変数にも必要なので、イベントを自動的に追加します。

## Cookie

addProductEvent プラグインは、Cookie を作成したり使用したりしません。

## 呼び出しの例

### 例 1

次のコードは、変数をに設 `s.products` 定しま `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`す。

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

上記のコードでは、変数 `s.events` を `"purchase,event35"`

### 例 2

次のコードでは、変数 `s.products` を `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

呼び出しの3番目の引数が `addProductEvent` (ま `true` たは `1`)の場合、各製品エントリの値には、呼び出しで指定されたイベントが追加されます。

### 例 3

次のコードでは、変数 `s.products` を `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

上記のコードでは、変数 `s.events` を `"purchase,event2,event33,event34,event35"`

### 例 4

次のコードでは、変数 `s.products` を `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

上記のコードでは、変数もに設 `s.events` 定されま `"purchase,event2,event33,event34,event35"`す。

>[!NOTE] 呼び出しの2番目の引数は、整数または **** 、整数/数値を表す文字列です

### 例 5

が設 `s.products` 定されていない場合、次のコードは `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

上記のコードも `"event35"` また、の末尾に付加 `s.events` さ **れ**`s.events` ます `s.events` 。まだ設定されていない場合は、上記のコードセットは、 `"event35"`

## バージョン履歴

### 1.0（2019 年 10 月 8 日）

* 初回リリース。
