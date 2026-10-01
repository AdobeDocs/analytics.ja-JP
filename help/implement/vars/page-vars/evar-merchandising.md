---
title: eVar（マーチャンダイジング変数）
description: 個々の製品に関連付けられるカスタム変数。
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/BdChWcR9AJqLZ0KjOxSvFAjB8-58JmmGahrpvTyFeFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 29%
---
# eVar（マーチャンダイジング）

>[!BEGINSHADEBOX]

*このヘルプページでは、マーチャンダイジング eVar の実装方法について説明します。 マーチャンダイジング eVarsがディメンションとして機能する方法について詳しくは、『コンポーネントユーザーガイド』の[eVar（マーチャンダイジングディメンション） ](/help/components/dimensions/evar-merchandising.md)を参照してください。*

>[!ENDSHADEBOX]

マーチャンダイジング eVarは個々の製品に値をバインドするため、各製品に関する成功イベントは、その製品にバインドされた値にクレジットされます。 値は、次のいずれかの方法で設定できます。

* **[!UICONTROL 製品構文]**: [`products`](products.md)変数の各製品の値を設定します。
* **[!UICONTROL コンバージョン変数構文]**: eVar自体で値を設定します。 値は、バインディングイベントを含むヒットの製品にバインドされます。

バインディング、割り当て、有効期限の仕組みについては、[eVar（マーチャンダイジングディメンション） ](/help/components/dimensions/evar-merchandising.md)を参照してください。

## レポートスイート設定での eVar の設定

実装で eVar を使用する前に、必ず、レポートスイートの設定で eVar を目的の構文に設定してください。 詳しくは、『管理者ガイド』の[コンバージョン変数](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)を参照してください。

>[!WARNING]
>
>マーチャンダイジング eVar を正しく設定しないと、変数の予期しない値やデータ損失が発生します。 お使いの実装に合わせて正しく設定されていることを確認します。

## 構文の選択

`products`変数の設定時にマーチャンダイジング値が使用可能な場合、または同じヒット内の製品で異なる値が必要な場合は、[!UICONTROL 製品構文]を使用します。 訪問者を製品に導いた検索語や内部キャンペーンなど、製品の前に値が既知の場合は、[!UICONTROL  コンバージョン変数構文]を使用します。 完全な比較については、[ バインディングと割り当ての仕組み](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)を参照してください。

## 製品の構文を使用して実装する

[!UICONTROL 製品構文]が有効になっている場合、マーチャンダイジング値は`products`変数内で直接設定されるので、バインディングイベントは使用されません。 マーチャンダイジング eVarは、各製品の最後のセグメントに配置されます。

```js
s.products = "[category];[name];[quantity];[revenue];[events];[eVars]";
```

同じ製品の複数のマーチャンダイジング eVarをパイプ （`|`）で区切ります。 数量、収益、イベントの空のプレースホルダーは、使用しない場合でも必要です。 このオプションを指定しない場合、eVar値は無視されます。

そのヒットの商品に値がバインドされます。 後の値が既存のバインディングを置き換えるかどうかは、[!UICONTROL 配分]設定によって異なります。 [ バインドと割り当ての仕組み](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)を参照してください。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

### Web SDK を使用した製品構文

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md)&#x200B;を使用する場合、製品構文マーチャンダイジング変数では次のXDM フィールドが使用されます。

* 製品構文マーチャンダイジング eVar は、`xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` から `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250` までにマッピングされます。
* 製品構文マーチャンダイジングイベントは、`xdm.productListItems[]._experience.analytics.event1to100.event1.value` から `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value` までにマッピングされます。 [イベントのシリアル化](events/event-serialization.md) XDM フィールドは、`xdm.productListItems[]._experience.analytics.event1to100.event1.id` から `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id` までにマッピングされます。

>[!NOTE]
>
>`productListItems` でイベントを設定する場合は、イベントをイベント文字列で設定する必要はありません。 両方で設定されている場合は、イベント文字列の値が優先されます。

次の例では、複数のマーチャンダイジング eVar およびイベントを使用した 1 つの[製品](products.md)を示します。

```json
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

上記の例のオブジェクトは、Adobe Analytics に `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"` として送信されることになります。

[**データオブジェクト**](/help/implement/aep-edge/data-var-mapping.md)&#x200B;を使用する場合、製品構文マーチャンダイジング eVarは`data.__adobe.analytics.products`に設定され、AppMeasurement `products`変数と同じ構文が使用されます。 上記のXDMの例に相当するデータオブジェクト：

```json
"data": {
  "__adobe": {
    "analytics": {
      "products": ";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"
    }
  }
}
```

## コンバージョン変数の構文を使用して実装する

EVar値を`products`変数に設定できない場合は、[!UICONTROL  コンバージョン変数構文]を使用します。 通常、このシナリオでは、商品ページにはマーチャンダイジングチャネルや検索方法に関するコンテキストがありません。 このような場合は、結合イベントが発生するページの上または前にマーチャンダイジング eVarを設定します。 値は、有効期限が切れるまで保持されるか、新しい値で上書きされます。

ヒットに`products`変数と選択した[!UICONTROL  マーチャンダイジングバインディングイベント ]の両方が含まれている場合、eVarの現在の値はそのヒットのすべての商品にバインドされます。 バインディングイベントを使用せずにeVarを製品と一緒に設定しても、値はバインドされません。 後のバインディングが既存のバインディングを置き換えるかどうかは、[!UICONTROL 配分]設定によって異なります。 [ バインドと割り当ての仕組み](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)を参照してください。

複数の製品検索方法eVarを一度に設定する例については、[ ベストプラクティス：製品検索方法](/help/components/dimensions/evar-merchandising.md#best-practice-product-finding-methods)を参照してください。

次の例では、バインディングイベントの前にマーチャンダイジング eVarを設定します。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

[!UICONTROL 製品ビューイベント ]がバインディングイベントである場合、`eVar1`の値`"Aviary"`は製品`"Canary"`にバインドされます。 この製品に関連するその後の成功イベントは`"Aviary"`にクレジットされます。 値`"Aviary"`は、次のいずれかの条件が満たされるまで、バインディングイベントを含む後のヒットの製品にもバインドされます。

* EVarの有効期限（[!UICONTROL 有効期限]設定に基づく）。
* マーチャンダイジング eVar が新しい値で上書きされる。

### Web SDK を使用したコンバージョン変数構文

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md)&#x200B;を使用する場合、構文は他の[eVars](evar.md)および[ イベント ](events/events-overview.md)の実装と同様に動作します。 [**データオブジェクト**](/help/implement/aep-edge/data-var-mapping.md)&#x200B;を使用する場合、構文はAppMeasurementに従います。

上記のAppMeasurementの例をミラーリングするXDMは、次のようになります。

同じまたは前のイベントコールで eVar を設定します。

```json
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

バインディングイベントと製品文字列の値を設定します。

```json
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

上記のAppMeasurementの例を反映したデータオブジェクトは、次のようになります。

同じまたは前のイベントコールで eVar を設定します。

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

バインディングイベントと製品文字列の値を設定します。

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```

