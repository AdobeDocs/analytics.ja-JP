---
title: addProductEvent
description: カスタムイベントを製品およびイベント変数に追加します。
translation-type: ht
source-git-commit: 3359ed8e7ef7979be57ca5ec9ca1803fc52afe88
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---


# Adobe プラグイン：addProductEvent

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`addProductEvent` プラグインは、数値イベントまたは通貨イベントを [`products`](../page-vars/products.md) 変数に追加します。製品文字列の形式を気にせずに数値イベントや通貨イベントを `products` 変数に追加する場合は、このプラグインを使用することをお勧めします。このプラグインは、`products` 変数で数値イベントや通貨イベントを使用しない場合は不要です。

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
   * Action Type：Initialize addProductEvent
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
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
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

次のコードは、 `s.products` 変数を `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"` に設定します。

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

また、上記のコードでは、`s.events` 変数を `"purchase,event35"` に設定します。

### 例 2

次のコードでは、`s.products` 変数を `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"` に設定します。

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

`addProductEvent` 呼び出しの 3 番目の引数が `true`（または `1`）の場合、呼び出しで指定されたイベントが各製品エントリの値に追加されます。

### 例 3

次のコードでは、`s.products` 変数を `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"` に設定します。

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

また、上記のコードでは、`s.events` 変数を `"purchase,event2,event33,event34,event35"` に設定します。

### 例 4

次のコードでは、`s.products` 変数を `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"` に設定します。

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

また、上記のコードでは、`s.events` 変数を `"purchase,event2,event33,event34,event35"` に設定します。

>[!NOTE]
>
>呼び出しの 2 番目の引数は、整数&#x200B;**または**&#x200B;整数／数値を表す文字列です

### 例 5

`s.products` がまだ設定されていない場合、次のコードによって `";;;;event35=25"` に設定されます。

```js
s.addProductEvent("event35", "25");
```

上記のコードでは、 `s.events` のの末尾に `"event35"` を追加します。**または** `s.events` がまだ設定されていない場合、上記のコードセットは `s.events` を `"event35"` に設定します。

## バージョン履歴

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2019 年 10 月 7 日（PT））

* 初回リリース。
