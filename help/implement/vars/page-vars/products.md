---
title: products
description: 表示される商品や買い物かごに関するデータを送信します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# products

この変数は `products` 、関連付けられた製品とプロパティを追跡します。 この変数は、通常、個々の製品ページ、買い物かごページ、および購入確認ページに設定されます。 これは複数値の変数で、同じヒットで複数の製品を送信し、アドビがその値を別々のディメンション値に解析します。

> [!NOTE] この変数が、買い物かごイベントのないヒットで変数に設定され [`events`](events/events-overview.md) た場合、「製品表示回数」指標の値は1増分されます。 各ヒットに適切な買い物かごイベントを設定していることを確認します。

## Adobe Experience Platform Launchの製品

この変数を設定するための専用フィールドが「起動」にありません。ただし、複数のサードパーティ拡張機能が存在しているので、これらの機能を利用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、をク [!UICONTROL Extensions] リックして使用可能なすべ [!UICONTROL Catalog] ての拡張機能を表示します。
4. 「product」という用語を検索すると、この変数の設定に役立ついくつかの拡張機能が表示されます。

これらの拡張機能の1つを使用するか、以下のAppMeasurement構文に従ってカスタムコードエディターを使用できます。

## AppMeasurementのs.productsとカスタムコードエディターの起動

変数は、 `s.products` 製品ごとに複数の区切られたフィールドを含む文字列です。 個々の製品には、すべてのフィールドに対して最大100バイトを含めることができます。 各フィールドは、文字列内でセミコロン(`;`)で区切ります。

* **カテゴリ** （オプション）:包括的な製品カテゴリ。 組織は、製品をカテゴリにグループ化する方法を決定します。
* **製品名** （必須）:製品の名前。
* **数量** （オプション）:買い物かごに入っている商品の数。 このフィールドは、購入イベントを含むヒットにのみ適用されます。
* **価格** （オプション）:10進法での製品の合計価格。 数量が複数の場合は、価格を個々の製品価格ではなく合計に設定します。 この値の通貨を変数に合わせて整列し [`currencyCode`](../config-vars/currencycode.md) ます。 このフィールドに通貨記号を含めないでください。 このフィールドは、購入イベントを含むヒットにのみ適用されます。
* **イベント** （オプション）:製品に関連付けられたイベント。 複数のイベントをパイプで区切ります(`|`)。 詳しくは [、events](events/events-overview.md) を参照してください。
* **eVar** （オプション）:製品に結び付けられたマーチャンダイジングeVar。 複数のマーチャンダイジングeVarをパイプで区切りま`|`す()。 詳しくは、マ [ーチャンダイジングeVar](../../../components/c-variables/c-merch-variables/var-merchandising.md) （マーチャンダイジングeVar）を参照してください。

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

この変数は、同じヒットで複数の製品をサポートします。 買い物かごや複数の製品を含む購入に役立ちます。 1つの製品につき100バイトの制限がありますが、変数の合計の長さ `products` は64Kです。 各製品は文字列内でコンマ(`,`)で区切ります。

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

> [!IMPORTANT] 製品名、カテゴリ、マーチャンダイジングeVarの値から、セミコロン、コンマ、パイプをすべて取り除きます。 製品名にコンマが含まれる場合、AppMeasurementは、その製品を新しい製品の最初として解析します。 この誤った解析は、製品文字列の残りの部分をスローし、ディメンションやレポートに誤ったデータが含まれる原因となります。

## 例

この変数 `products` は、フィールドを省略し、複数の製品を含める場合に柔軟に使用できます。 この柔軟性により、区切り文字を見逃しやすくなり、導入時に誤ったデータがアドビに送信される原因となります。

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product,;Example product";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```
