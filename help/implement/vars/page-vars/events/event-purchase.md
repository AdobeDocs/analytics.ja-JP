---
title: 購入イベント
description: 購入イベントを使用して、「注文件数」、「数量」および「売上高」指標のデータを収集します。
feature: Appmeasurement Implementation
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/r-L330P6HA5qWBmEW-2LwECo-d3dhVK1ovWsfraErXE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 66%

---

# 購入イベント

購入イベントは `events` 変数内の値です。 この値は、サイトが生み出す売上高に関するデータを収集する組織に役立ちます。 購入イベントは、[`products`](../products.md) 変数と [`purchaseID`](../purchaseid.md) 変数に大きく依存します。

購入イベントを設定すると、次の指標に影響します。

* 「注文件数」指標は 1 増分されます
* 「数量」指標は、`products` 変数内の製品数だけ増分されます
* 「売上高」指標は、`products` 変数内の価格パラメーターの合計で増加します

>[!NOTE]
>
>売上高に数量フィールドを掛けることはありません。 例えば、`s.products="Womens;Socks;5;4.50"`は$22.50を収益に渡しません。$4.50を渡します。 実装がリストされた数量の総収益を通過していることを確認してください。 例：`s.products="Womens;Socks;5;22.50"`。

## Web SDKを使用した購入イベントの設定

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md)&#x200B;を使用する場合、購入イベントでは次のXDM フィールドが使用されます。

* 注文件数は、`xdm.commerce.purchases.value` にマッピングされます。
* 単位は、すべての `xdm.productListItems[].quantity` フィールドの合計にマッピングされます。 詳しくは、[`products`](../products.md)を参照してください。
* 売上高は、すべての `xdm.productListItems[].priceTotal` フィールドの合計にマッピングされます。

```json
{
  "xdm": {
    "commerce": {
      "purchases": {
        "value": 1
      }
    }
  }
}
```

[**データオブジェクト**](/help/implement/aep-edge/data-var-mapping.md)&#x200B;を使用する場合、購入イベントはAppMeasurement文字列構文に従って`data.__adobe.analytics.events`を使用します。

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "events": "purchase"
      }
    }
  }
}
```

## Adobe Analytics拡張機能を使用した購入イベントの設定

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. 「[!UICONTROL  イベント ]」セクションを見つけ、[!UICONTROL  イベント ] ドロップダウンリストを[!UICONTROL 購入]に設定します。

`products`や`purchaseID`などの他の依存変数には、Adobe Experience Platform Data Collection内のAnalytics拡張機能に専用フィールドがありません。 これらの変数については、AppMeasurement 構文に従ったカスタムコードエディターを使用します。

## AppMeasurementとAnalytics拡張機能のカスタムコードエディターで購入イベントを設定します

購入イベントは、イベント変数の一部として設定される文字列です。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 購入イベントの重複除外

購入イベントを発生させると、アドビは次の項目を確認します。

* ヒットに `purchaseID` 変数が含まれているか。 そうでない場合、アドビはヒットの情報を使用して「一時的な購入 ID」を作成します。 この一時的な購入 ID は、ヒットの訪問者にのみ適用されます。 以前の 5 つの一時的な購入 ID は、（レポートスイートごとに）各訪問者 ID に対して保存されます。
* 一時的な購入 ID が、保存されている最近 5 つの一時的な購入 ID のいずれかに一致するか。 その場合、イメージリクエストは重複した購入とみなされます。 購入イベントを含むすべてのコンバージョン変数がレポートに表示されません。
* `purchaseID` 変数が定義されている場合、すべての訪問者に対してレポートスイートで既に収集されている値と一致するか。 その場合、イメージリクエストは重複した購入とみなされます。 購入イベントを含むすべてのコンバージョン変数がレポートに表示されません。
