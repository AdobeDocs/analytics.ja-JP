---
title: 製品
description: 表示される製品や買い物かごに含まれる製品に関するデータを送信します。
feature: Appmeasurement Implementation
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 67%

---

# 製品

`products` 変数は、それらに関連付けられた製品とプロパティを追跡します。この変数は、通常、個々の製品ページ、買い物かごページ、および購入確認ページに設定されます。これは複数値の変数で、同じヒットで複数の製品を送信し、アドビがその値を別々のディメンション項目に解析します。

>[!NOTE]
>
>この変数が、[`events`](events/events-overview.md) 変数のないヒットで設定されている場合、[製品表示回数](/help/components/metrics/product-views.md)指標は 1 増分されます。各ヒットに対して、`products` 変数を使用して適切なイベントを設定していることを確認します。

## Web SDKを使用した製品

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md) を使用する場合、製品は次の変数にマッピングされます。

* カテゴリは `xdm.productListItems[].productCategories[].categoryID` にマッピングされます。 `productCategories[]` 配列の最初の項目を使用します。 `lineItemId` も正しくマッピングされますが、Adobeでは標準 XDM なので `categoryID` を使用することをお勧めします。 両方の XDM フィールドが存在する場合は、`lineItemId` が優先されます。
* 製品は `xdm.productListItems[].SKU` または `xdm.productListItems[].name` にマップされています。 両方の XDM フィールドが存在する場合は、`xdm.productListItems[].SKU` が使用されます。
* 数量は `xdm.productListItems[].quantity` にマッピングされます。
* 価格は `xdm.productListItems[].priceTotal` にマッピングされます。
* マーチャンダイジング eVar は、商品にバインドするeVarに応じて、`xdm.productListItems._experience.analytics.customDimensions.eVars.eVar1` から `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar250` にマッピングされます。
* マーチャンダイジングイベントは、製品にバインドするイベントに応じて、`xdm.productListItems[]._experience.analytics.event1to100.event1.value`～`xdm.productListItems._experience.analytics.event901to1000.event1000.value` にマッピングされます。 これらのフィールドのいずれかにイベントを設定すると、Adobe Analyticsに送信される [event](events/events-overview.md) 文字列に自動的に含まれます。

```json
{
  "xdm": {
    "productListItems": [{
      "productCategories": [{
        "categoryID": "Men's"
      }],
      "name": "Hiking boot",
      "quantity": 1,
      "priceTotal": 49.99
    },
    {
      "productCategories": [{
        "categoryID": "Camping"
      }],
      "name": "Hunting blind",
      "quantity": 3,
      "priceTotal": 699.69
    }]
  }
}
```

[**data オブジェクト**](/help/implement/aep-edge/data-var-mapping.md) を使用する場合、products 変数は次のAppMeasurement構文 `data.__adobe.analytics.products` 使用します。 このフィールドを設定すると、XDM オブジェクトで設定された商品は上書きされ、Adobe Analyticsには送信されません。

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Archery;Fletched arrow;12;159.99"
      }
    }
  }
}
```

## Adobe Analytics拡張機能を使用した製品

Adobe Experience Platform Data Collection には、この変数を設定する専用のフィールドはありませんが、サードパーティ拡張機能が複数存在しています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」をクリックして、使用可能な拡張機能をすべて表示します。
4. 「product」という用語を検索すると、この変数の設定に役立ついくつかの拡張機能が明らかになります。

これらの拡張機能の 1 つを使用することも、以下の AppMeasurement 構文に従ってカスタムコードエディターを使用することもできます。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.products

`s.products` 変数は、製品ごとに複数の区切りフィールドを含む文字列です。文字列内の各フィールドをセミコロン（`;`）で区切ります。

* **カテゴリ** （任意）：製品のカテゴリです。 このフィールドの最大長は 100 バイトです。
* **製品名**（必須）：製品の名前。このフィールドの最大長は 100 バイトです。
* **量**（任意）：買い物かごに入っている製品の数。このフィールドは、購入イベントを含むヒットにのみ適用されます。
* **価格**（任意）：小数での製品の合計価格。量が 2 つ以上の場合、価格は個々の製品価格ではなく合計に設定します。この値の通貨を [`currencyCode`](../config-vars/currencycode.md) 変数に合わせて整列します。このフィールドに通貨記号を含めないでください。このフィールドは、購入イベントを含むヒットにのみ適用されます。
* **イベント**（任意）：製品に関連付けられたイベント。複数のイベントをパイプ（`|`）で区切ります。詳しくは、 [イベント](events/events-overview.md) を参照してください。
* **eVar**（任意）：製品に結び付けられたマーチャンダイジング eVar。複数のマーチャンダイジング eVar はパイプ（`|`）で区切ります。詳しくは、 [マーチャンダイジング eVar](evar-merchandising.md) を参照してください。

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

この変数は、同じヒットで複数の製品をサポートします。買い物かごや複数の製品を含む購入に役立ちます。`products` 文字列全体の最大長は 64k バイトです。 各製品は文字列内でコンマ（`,`）で区切ります。

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
