---
title: addProductEvent
description: カスタムイベントを製品およびイベント変数に追加します。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobeプラグイン：addProductEvent

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `addProductEvent` ラグインは、数値イベントまたは通貨イベントを変数に追加 `products` します。 製品文字列の形式を気にせずに数値イベントや通貨イベントを変数に追加する場合は、このプ `products` ラグインを使用することをお勧めします。 このプラグインは、変数で数値イベントや通貨イベントを使用しない場合は不要 `products` です。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * 条件：なし
   * イベント：コア — ライブラリ読み込み済み（ページの上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：addProductEventの初期化
1. ルールに対する変更を保存して発行します。

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
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `addProductEvent` ッドでは、次の引数を使用します。

* **`en`**（必須、文字列）:変数の最後のエントリに追加するイベ`products`ント。 変数が空`products`の場合、イベント（およびその値）が添付された「空白」の製品エントリが作成されます。
* **`ev`**（必須、文字列）:引数内の数値イベントまたは通貨イベントに割り当てられ`en`る値。  未設定の場`1`合はデフォルトです。
* **`ap`**（オプション、ブール値）:現在、products変数に複数の製品エントリが含まれている場合、値が（または）の`true`場合、すべての製`1`品エントリにイベントが追加されます。  未設定の場`false`合はデフォルトです。

は何も `addProductEvent` 返しません。 代わりに、イベントとその値が変数に追加され `products` ます。 また、このプラグインは変数にも必要なので、 `events` イベントを自動的に追加します。

## Cookie

addProductEventプラグインは、cookieを作成したり使用したりしません

## 呼び出しの例

### 例1

...

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase"
```

...次のコードが実行されます。

```js
s.addProductEvent("event35", "25");
```

...s.productsの最終的な価値は次のとおりです。

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25;event35=25"
```

...s.eventsの最後の値は次のようになります。

```js
s.events="purchase,event35"
```

### 例2

...

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
```

...次のコードが実行されます。

```js
s.addProductEvent("event35", 25, 1);
```

...s.productsの最終的な価値は次のとおりです。

```js
s.products=";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"
```

3番目の引数がtrue（または1）の場合、各製品エントリの値に呼び出しで指定されたイベントが追加されます

### 例3

...

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
```

...次のコードが実行されます。

```js
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

...s.productsの最終価値は…となる。

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"
```

...とs.eventsは次のように設定されます。

```js
s.events="purchase,event2,event33,event34,event35"
```

### 例4

...

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
```

...次のコードが実行されます。

```js
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1); //The second argument can be an integer or a string representing an integer/number
s.addProductEvent("event35", "15", 1);
```

...s.productsの最終価値は…となる。

```js
s.products=";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"
```

...とs.eventsは次のように設定されます。

```js
s.events="purchase,event2,event33,event34,event35"
```

### 例5

s.productsが設定されていない場合、次のコードが実行されます。

```js
s.addProductEvent("event35", "25");
```

...s.productsの最終的な価値は次のとおりです。

```js
s.products=";;;;event35=25"
```

この場合、event35もs.eventsの末尾に追加されます。

## バージョン履歴

### 1.0（2019年10月8日）

* 初回リリース。
