---
title: 購入イベント
description: 購入イベントを使用して、「注文件数」、「数量」および「売上高」指標のデータを収集します。
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 75%

---

# 購入イベント

購入イベントは `events` 変数内の値です。この値は、サイトが生み出す売上高に関するデータを収集する組織に役立ちます。購入イベントは、[`products`](../products.md) 変数と [`purchaseID`](../purchaseid.md) 変数に大きく依存します。

購入イベントを設定すると、次の指標に影響します。

* 「注文件数」指標は 1 増分されます
* 「数量」指標は、`products` 変数内の製品数だけ増分されます
* 「売上高」指標は、`products` 変数内の価格パラメーターの合計で増加します

>[!NOTE]
>
>売上高に数量フィールドを掛けることはありません。例： `s.products="Womens;Socks;5;4.50"` は$22.50 を売上高に渡しません。$4.50 を渡します。実装に、リストされている量に対する合計売上高を渡すようにしてください。 例：`s.products="Womens;Socks;5;22.50"`。

## Web SDK を使用した購入イベントの設定

購入イベントは [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) 複数の XDM フィールドの下：

* 注文件数は、`commerce.purchases.value` にマッピングされます。
* 単位は、すべての `productListItems[].quantity` フィールドの合計にマッピングされます。
* 売上高は、すべての `productListItems[].priceTotal` フィールドの合計にマッピングされます。

## Adobe Analytics拡張機能を使用した購入イベントの設定

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. を [!UICONTROL 拡張] Adobe Analyticsのドロップダウンリスト [!UICONTROL アクションタイプ] から [!UICONTROL 変数を設定].
6. を [!UICONTROL イベント] セクションを選択し、 [!UICONTROL イベント] ドロップダウンリスト [!UICONTROL 購入].

その他の依存変数 ( `products` および `purchaseID` Adobe Experience Platformデータ収集内の Analytics 拡張機能に専用フィールドがない。 これらの変数については、AppMeasurement 構文に従ったカスタムコードエディターを使用します。

## AppMeasurement と Analytics 拡張機能のカスタムコードエディターでの購入イベントの設定

購入イベントは、イベント変数の一部として設定される文字列です。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 購入イベントの重複除外

購入イベントを発生させると、アドビは次の項目を確認します。

* ヒットに `purchaseID` 変数が含まれているか。そうでない場合、アドビはヒットの情報を使用して「一時的な購入 ID」を作成します。この一時的な購入 ID は、ヒットの訪問者にのみ適用されます。以前の 5 つの一時的な購入 ID は、（レポートスイートごとに）各訪問者 ID に対して保存されます。
* 一時的な購入 ID が、保存されている最近 5 つの一時的な購入 ID のいずれかに一致するか。一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
* `purchaseID` 変数が定義されている場合、すべての訪問者に対してレポートスイートで既に収集されている値と一致するか。一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
