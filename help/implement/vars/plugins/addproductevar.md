---
title: addProductEvar
description: 商品変数にマーチャンダイジングeVarを追加します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：addProductEvar

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `addProductEvar` ラグインを使用すると、既に存在する製品変数の内容が変更/移動/削除されるかどうかを気にすることなく、製品構文を使用するAdobe AnalyticsマーチャンダイジングeVarを製品変数に簡単に追加できます。 製品構文のマーチャンダイジングeVarを簡単に変数に追加する場合は、このプラグインの使用をお勧め [`products`](../page-vars/products.md) します。 製品の構文でマーチャンダイジングeVarを使 `addProductEvar` 用しない場合は、プラグインを使用する必要はありません。

> [!NOTE] このプラグインは、製品エントリに既に存在するeVarを置き換えません。 このプラグインを使用して設定した値のみが追加されます。 その製品に既に存在するeVarを追加する場合は注意が必要です。

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
   * アクションタイプ：addProductEvarの初期化
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
/* Adobe Consulting Plugin: addProductEvar v1.0 */
s.addProductEvar=function(en,ev,ap){if("string"===typeof en&&"string"===typeof ev&&""!==ev)if(ap=ap||!1,this.products){var e=this.products.split(","),f=e.length;ap=ap?0:f-1;for(var a;ap<f;ap++)a=e[ap].split(";"),a[5]&&-1<a[5].toLowerCase().indexOf("evar")?a[5]=a[5]+"|"+en+"="+ev:a[5]?a[5]=en+"="+ev:a[5]||(a[4]||(a[4]=""),a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[5]=en+"="+ev),e[ap]=a.join(";");this.products=e.join(",")}else this.products=";;;;;"+en+"="+ev};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

プラグ `addProductEvar` インは次の引数を使用します。

* **`en`** （必須、文字列）:現在products変数に含まれている最後のエントリに追加するeVar。 products変数が空白の場合、プラグインは「空白の」製品エントリを作成し、そのエントリの末尾にeVar値を付加します。
* **`ev`** （必須、文字列）:eVarに割り当てられた値。
* **`ap`** （オプション、ブール値）:現在、products変数に複数の製品エントリが含まれている場合、値がtrue（または1）の場合、すべての製品エントリにeVar **が** 追加されます。  デフォルトはfalse（または0）で、eVarはproducts変数に含まれる最後の **エントリ** のみに追加されます。

プラグイン `addProductEvar` は何も返しません。 代わりに、引数とで指定したeVar（およびeVar値）が変 `en` 数に `ev` 追加され `products` ます。

## 例

```js
// Set a merchandising eVar to blue on the last product. The output for the products variable is ";product1;3;300,;product2;2;122,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar1", "blue");

// Set a merchandising eVar to blue on all products. The output for the products variable is ";product1;3;300;;eVar1=blue,;product2;2;122;;eVar1=blue,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar1", "blue", true);

// Set multiple merchandising eVars to the last product in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar23", "medium");
s.addProductEvar("eVar24", "women");
s.addProductEvar("eVar1", "red");

// Set multiple merchandising eVars to all products in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue|eVar23=medium|eVar24=women|eVar1=red,;product2;2;122;;eVar23=medium|eVar24=women|eVar1=red,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
s.addProductEvar("eVar23", "medium", true);
s.addProductEvar("eVar24", "women", true);
s.addProductEvar("eVar1", "red", true);

// If the products variable is not set, the plug-in creates an empty product string correctly delimited to the merchandising eVar. The output for the products variable is ";;;;;eVar1=blue"
s.addProductEvar("eVar1", "blue");
```

## バージョン履歴

### 1.0（2019年10月8日）

* 初回リリース。
