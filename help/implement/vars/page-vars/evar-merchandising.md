---
title: eVar（マーチャンダイジング）
description: 個々の製品に関連付けられるカスタム変数。
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 29%

---


# eVar（マーチャンダイジング）

*このヘルプページでは、マーチャンダイジングeVarを実装する方法について説明します。 マーチャンダイジングeVarがディメンションとして機能する方法について詳しくは、コンポーネントユーザーガイドのeVar（マーチャンダイジング）[](/help/components/dimensions/evar-merchandising.md)を参照してください。*

## レポートスイート設定での eVar の設定

実装でeVarを使用する前に、レポートスイートの設定でeVarを目的の構文に設定してください。 詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)を参照してください。

>[!IMPORTANT] マーチャンダイジングeVarを正しく設定しないと、変数の予期しない値やデータ損失が発生します。 お使いの実装に合わせて正しく設定されていることを確認します。

## 製品の構文を使用した実装

When &#39;Product Syntax&#39; is enabled, the merchandising category is populated directly within the `products` variable, so selecting and setting a binding event is not required. これが推奨される方法であり、成功イベントが発生したときにその値を `products` に設定できない場合を除いて、この方法を使用してください。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

の値 `eVar1` が製品に割り当てられます。 この商品を含む以降の成功イベントはすべてeVar値に配分されます。

## コンバージョン変数の構文を使用した実装

Conversion Variable Syntax is used when the eVar value is not available to set in the `products` variable. 通常、このシナリオは、ページにマーチャンダイジングチャネルや検索方法のコンテキストがないことを意味します。 このような場合は、商品ページに到達する前にマーチャンダイジング変数を設定し、その値がバインディングイベントが発生するまで保持されます。

設定時にバインディングイベントが選択されると、保持された eVar の値が製品に関連付けられます。For example, if `prodView` is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. 既に製品に割り当てられているマーチャンダイジング eVar を更新できるのは、以降のバインディングイベントのみです。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

の値 `"Aviary"` が製品に割り当 `eVar1` てられ `"Canary"`ます。 この商品に関連する以降の成功イベントはすべて、にクレジットが付与され `"Canary"`ます。 さらに、以下のどちらかの条件が満たされるまで、マーチャンダイジング変数の現在の値が以後のすべての製品に結び付けられます。

* eVarの有効期限が切れる（「有効期限」の設定に基づきます）。
* マーチャンダイジング eVar が新しい値で上書きされる。
