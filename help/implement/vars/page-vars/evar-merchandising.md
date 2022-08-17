---
title: eVar（マーチャンダイジング）変数
description: 個々の製品に関連付けられるカスタム変数。
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
source-git-commit: e8a6400895110a14306e2dc9465e5de03d1b5d73
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 75%

---

# eVar（マーチャンダイジング）

*このヘルプページでは、マーチャンダイジング eVar の実装方法について説明します。マーチャンダイジング eVar がディメンションとして機能する方法について詳しくは、『コンポーネントユーザガイド』の [eVar](/help/components/dimensions/evar-merchandising.md) を参照してください。*

マーチャンダイジング eVar の仕組みについて詳しくは、[マーチャンダイジング eVar と製品検索方法](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=ja)を参照してください。

## レポートスイート設定での eVar の設定

実装で eVar を使用する前に、各 eVar をレポートスイートの設定で設定してください。詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を参照してください。

>[!WARNING]
>
>マーチャンダイジング eVar を正しく設定しないと、変数の予期しない値やデータ損失が発生します。お使いの実装に合わせて正しく設定されていることを確認します。

## 製品の構文を使用した実装

「製品の構文」が選択されている場合、マーチャンダイジングカテゴリーが `products` 変数に直接入力されるので、バインディングイベントを選択して設定する必要はありません。これが推奨される方法であり、成功イベントが発生したときにその値を `products` に設定できない場合を除いて、この方法を使用してください。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

`eVar1` の値が製品に割り当てられます。この製品を含む以降の成功イベントはすべて eVar 値に配分されます。

### Web SDK を使用した製品構文

製品構文マーチャンダイジング変数は、 [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) 複数の異なる XDM フィールドの下に

* 製品構文マーチャンダイジング eVar は、 `productListItems[]._experience.analytics.customDimensions.eVars.eVar1` から `productListItems[]._experience.analytics.customDimensions.eVars.eVar250`.
* 製品構文マーチャンダイジングイベントは、 `productListItems[]._experience.analytics.event1to100.event1.value` から `productListItems[]._experience.analytics.event901to1000.event1000.value`. [イベントのシリアル化](events/event-serialization.md) XDM フィールドは、の下にマッピングされます。 `productListItems[]._experience.analytics.event1to100.event1.id` から `productListItems[]._experience.analytics.event901to1000.event1000.id`.

次の例は、 [製品](products.md) 複数のマーチャンダイジング eVar およびイベントの使用：

```js
"productListItems": [
    {
        "name": "Bahama Shirt",
        "priceTotal": "12.99",
        "quantity": 3,
        "_experience": {
            "analytics": {
                "customDimensions" : {
                    "eVars" : {
                        "eVar10" : "green",
                        "eVar33" : "large"
                    }
                },
                "event1to100" : {
                    "event4" : {
                        "value" : 1
                    },
                    "event10" : {
                        "value" : 2,
                        "id" : "abcd"
                    }
                }
            }
        }
    }
]
```

上記の例のオブジェクトは、Adobe Analyticsに `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"`.

## コンバージョン変数の構文を使用した実装

eVar 変数を `products` に設定できない場合、コンバージョン変数の構文を使用する必要があります変数。このシナリオは一般的には、ページにマーチャンダイジングチャネルや検索方法のコンテキストがない場合です。そのような場合、製品ページに到達する前にマーチャンダイジング変数を設定し、その値がバインディングイベントの発生時まで保持されるようにします。

設定時にバインディングイベントが選択されると、保持された eVar の値が製品に関連付けられます。例えば、バインディングイベントとして `prodView` が指定されている場合、イベントの発生時にのみ現在の製品リストにマーチャンダイジングカテゴリーが結び付けられます。既に製品に割り当てられているマーチャンダイジング eVar を更新できるのは、以降のバインディングイベントのみです。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

`eVar1` に `"Aviary"` の値が製品に割り当てられます`"Canary"`。この製品に関連する以降の成功イベントのクレジットはすべて `"Canary"` に付与されます。さらに、以下のどちらかの条件が満たされるまで、マーチャンダイジング変数の現在の値が以後のすべての製品に結び付けられます。

* eVar の期限が切れます（「有効期限」の設定に基づきます）。
* マーチャンダイジング eVar が新しい値で上書きされる。

### Web SDK を使用したコンバージョン変数の構文

Web SDK を使用したコンバージョン変数構文の動作は、他の [eVar](evar.md) および [イベント](events/events-overview.md). 上記の例の XDM ミラーリングは、次のようになります。

同じまたは前のeVar呼び出しに対して次のイベントを設定します。

```js
"_experience": {
    "analytics": {
        "customDimensions": {
            "eVars": {
                "eVar1" : "Aviary"
            }
        }
    }
}
```

製品文字列のバインディングイベントと値を設定します。

```js
"commerce": {
    "productViews" : {
        "value" : 1
    }
},
"productListItems": [
    {
        "name": "Canary"
    }
]
```
