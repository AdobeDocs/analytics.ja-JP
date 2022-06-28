---
title: 製品
description: 表示される製品や買い物かごに含まれる製品に関するデータを送信します。
feature: Variables
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
source-git-commit: 3edb7208f4b11a2fa58a2f7c696444ab998a6bfe
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 78%

---

# 製品

`products` 変数は、それらに関連付けられた製品とプロパティを追跡します。この変数は、通常、個々の製品ページ、買い物かごページ、および購入確認ページに設定されます。これは複数値の変数で、同じヒットで複数の製品を送信し、アドビがその値を別々のディメンション項目に解析します。

>[!NOTE]
>
>この変数が、[`events`](events/events-overview.md) 変数のないヒットで設定されている場合、[製品表示回数](/help/components/metrics/product-views.md)指標は 1 増分されます。各ヒットに対して、`products` 変数を使用して適切なイベントを設定していることを確認します。

## Web SDK を使用する製品

製品は [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) 複数の XDM フィールドの下：

* カテゴリのマッピング先 `productListItems[].lineItemId`.
* 製品が `productListItems[].name`.
* 数量が次にマッピングされています： `productListItems[].quantity`.
* 価格は `productListItems[].priceTotal`.
* マーチャンダイジング eVar は `productListItems._experience.analytics.customDimensions.eVars.eVar1` から `productListItems._experience.analytics.customDimensions.eVars.eVar250`に含まれ、製品にバインドするeVarに応じて異なります。
* マーチャンダイジングイベントのマッピング先 `productListItems[]._experience.analytics.event1to100.event1.value` から `productListItems._experience.analytics.event901to1000.event1000.value`に含まれ、製品にバインドするイベントに応じて異なります。

## Adobe Analytics拡張機能を使用する製品

Adobe Experience Platformデータ収集にこの変数を設定するための専用フィールドはありません。ただし、役に立つ複数のサードパーティの拡張機能が存在します。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」をクリックして、使用可能な拡張機能をすべて表示します。
4. 「product」という用語を検索すると、この変数の設定に役立ついくつかの拡張機能が明らかになります。

これらの拡張機能の 1 つを使用することも、以下の AppMeasurement 構文に従ってカスタムコードエディターを使用することもできます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.products

`s.products` 変数は、製品ごとに複数の区切りフィールドを含む文字列です。文字列内の各フィールドをセミコロン（`;`）で区切ります。

* **カテゴリ** （オプション）:商品カテゴリ。 このフィールドの最大長は 100 バイトです。
* **製品名**（必須）：製品の名前。このフィールドの最大長は 100 バイトです。
* **量**（オプション）：買い物かごに入っている製品の数。このフィールドは、購入イベントを含むヒットにのみ適用されます。
* **価格**（オプション）：小数での製品の合計価格。量が 2 つ以上の場合、価格は個々の製品価格ではなく合計に設定します。この値の通貨を [`currencyCode`](../config-vars/currencycode.md) 変数に合わせて整列します。このフィールドに通貨記号を含めないでください。このフィールドは、購入イベントを含むヒットにのみ適用されます。
* **イベント**（オプション）：製品に関連付けられたイベント。複数のイベントをパイプ（`|`）で区切ります。詳しくは、 [イベント](events/events-overview.md) を参照してください。
* **eVar**（オプション）：製品に結び付けられたマーチャンダイジング eVar。複数のマーチャンダイジング eVar はパイプ（`|`）で区切ります。詳しくは、 [マーチャンダイジング eVar](evar-merchandising.md) を参照してください。

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

この変数は、同じヒットで複数の製品をサポートします。買い物かごや複数の製品を含む購入に役立ちます。`products` 文字列全体の最大長は 64K です。各製品は文字列内でコンマ（`,`）で区切ります。

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
> 製品名、カテゴリ、マーチャンダイジング eVar の値から、セミコロン、コンマ、およびパイプをすべて取り除きます。製品名にコンマが含まれる場合、AppMeasurement は、それを新しい製品の開始として解析します。この誤った解析は、製品文字列の残りの部分をスローし、ディメンションやレポートに誤ったデータが含まれる原因となります。

## 例

`products` 変数は、フィールドを省略し、複数の製品を含める場合に柔軟に使用できます。この柔軟性により、区切り文字を見逃しやすくなり、実装によって誤ったデータがアドビに送信される原因となります。

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合は、`digitalData.product`オブジェクト配列を繰り返し処理できます。

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```
