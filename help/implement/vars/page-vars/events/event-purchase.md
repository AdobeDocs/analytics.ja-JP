---
title: 購入イベント
description: 購入イベントを使用して、「注文件数」、「数量」および「売上高」指標のデータを収集します。
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# 購入イベント

購入イベントは `events` 変数内の値です。この値は、サイトが生み出す売上高に関するデータを収集する組織に役立ちます。購入イベントは、[`products`](../products.md) 変数と [`purchaseID`](../purchaseid.md) 変数に大きく依存します。

購入イベントを設定すると、次の指標に影響します。

* 「注文件数」指標は 1 増分されます
* 「数量」指標は、`products` 変数内の製品数だけ増分されます
* 「売上高」指標は、`products` 変数内の価格パラメーターの合計で増加します

>[!NOTE]
>
>売上高に数量フィールドを掛けることはありません。例えば、`s.products="Womens;Socks;5;4.50"` では $22.50 ではなく、$4.50 が売上高に渡されます。実装において、リストされている量に対する合計売上高を渡すようにしてください。例： `s.products="Womens;Socks;5;22.50"`。

## Adobe Experience Platform Launch での購入イベントの設定

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL イベント]セクションを探し、「イベント」ドロップダウンを「[!UICONTROL 購入]」に設定します。

`products` と `purchaseID` など、その他の依存変数については、Launch に専用フィールドがありません。これらの変数については、AppMeasurement 構文に従ったカスタムコードエディターを使用します。

## AppMeasurement と Launch カスタムコードエディターでの購入イベントの設定

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
