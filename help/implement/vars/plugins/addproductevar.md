---
title: addProductEvar
description: マーチャンダイジング eVar を products 変数に追加します。
feature: Variables
exl-id: 6be94a15-78c9-4cbc-8b33-4a16f1b73b96
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 97%

---

# アドビプラグイン：addProductEvar

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`addProductEvar` プラグインを使用すると、既に存在する製品変数の内容が変更、移動、削除されるかどうかを気にすることなく、製品構文を使用する Adobe Analytics マーチャンダイジング eVar を products 変数に簡単に追加できます。製品構文マーチャンダイジング eVar を簡単に [`products`](../page-vars/products.md) 変数に追加するには、このプラグインを使用することをお勧めします。製品構文でマーチャンダイジング eVar を使用しない場合は、`addProductEvar` プラグインを使用する必要はありません。

>[!NOTE]
>
> このプラグインは、製品エントリに既に存在する eVar を置き換えません。このプラグインを使用して設定した値のみが追加されます。その製品に既に存在する eVar を追加する場合は注意が必要です。

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize addProductEvar
1. Save and publish the changes to the rule.-->

## カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvar v2.0 */
function addProductEvar(en,ev,ap){var e=en,f=ev,d=ap;if("-v"===e)return{plugin:"addProductEvar",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}if("undefined"!==typeof b&&(b.contextData.addProductEvar="2.0","string"===typeof e&&"string"===typeof f&&""!==f))if(d=d||!1,b.products){c=b.products.split(",");var g=c.length;d=d?0:g-1;for(var a;d<g;d++)a=c[d].split(";"),a[5]&&-1<a[5].toLowerCase().indexOf("evar")?a[5]=a[5]+"|"+e+"="+f:a[5]?a[5]=e+"="+f:a[5]||(a[4]||(a[4]=""),a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[5]=e+"="+f),c[d]=a.join(";");b.products=c.join(",")}else b.products=";;;;;"+e+"="+f};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`addProductEvar` プラグインは次の引数を使用します。

* **`en`**（必須、文字列）：現在 products 変数に含まれている最後のエントリに追加する eVar。products 変数が空白の場合、プラグインは「空白の」製品エントリを作成し、そのエントリの末尾に eVar 値を付加します。
* **`ev`**（必須、文字列）：eVar に割り当てられた値。
* **`ap`**（オプション、ブール値）：現在、products 変数に複数の製品エントリが含まれている場合、値が true（または 1）の場合、**すべて**&#x200B;の製品エントリに eVar が追加されます。デフォルトは false（または 0）で、eVar が products 変数に含まれる&#x200B;**最後の**&#x200B;エントリのみに追加されます。

`addProductEvar` プラグインは何も返しません。代わりに、`en` と `ev` 引数で指定された eVar（および eVar 値）を `products` 変数に追加します。

## 例

```js
// Set a merchandising eVar to blue on the last product. The output for the products variable is ";product1;3;300,;product2;2;122,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
addProductEvar("eVar1", "blue");

// Set a merchandising eVar to blue on all products. The output for the products variable is ";product1;3;300;;eVar1=blue,;product2;2;122;;eVar1=blue,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
addProductEvar("eVar1", "blue", true);

// Set multiple merchandising eVars to the last product in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
addProductEvar("eVar23", "medium");
addProductEvar("eVar24", "women");
addProductEvar("eVar1", "red");

// Set multiple merchandising eVars to all products in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue|eVar23=medium|eVar24=women|eVar1=red,;product2;2;122;;eVar23=medium|eVar24=women|eVar1=red,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
addProductEvar("eVar23", "medium", true);
addProductEvar("eVar24", "women", true);
addProductEvar("eVar1", "red", true);

// If the products variable is not set, the plug-in creates an empty product string correctly delimited to the merchandising eVar. The output for the products variable is ";;;;;eVar1=blue"
addProductEvar("eVar1", "blue");
```

## バージョン履歴

### 2.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2019 年 10 月 7 日（PT））

* 初回リリース。
