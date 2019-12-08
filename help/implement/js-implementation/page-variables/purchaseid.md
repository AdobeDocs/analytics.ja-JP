---
description: Adobe Analyticsに重複する購入が表示されるのを防ぐためのpurchaseID変数について説明します。
keywords: duplicate,purchase,purchaseid,s.purchaseid
subtopic: Variables
title: purchaseID
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# purchaseID

The `purchaseID` variable is used to keep an order from being counted multiple times in reporting. Whenever the purchase event is used on your site, Adobe recommends using the `purchaseID` variable.

訪問者がサイトで品目を購入すると、通常は「ご注文 `purchaseID` ありがとうございました」ページまたは「ご注文の確認」ページに値が設定されます。 購入イベン `purchaseID` トが発生するのと同時に、変数を設定します。 が一意 `purchaseID` の値に定義されている場合、コンバージョン変数の値は、その一意の購入IDを持つヒットに対してのみカウントされます。 訪問者は、購入確 `purchaseID` 認ページを自分の目的のために一般的にブックマークするので、このページの定義は役に立ちます。 導入で使用しない場合、訪問者がペ `purchaseID`ージを更新すると、コンバージョンデータ（売上高など）が容易に水増しされる可能性があります。

購入データに加えて、同じ購入IDを持つヒットに対して、すべてのコンバージョン変数およびイベントが複数回カウントされることはありません。

## 構文

この変 `purchaseID` 数は、最大20バイトの任意の英数字の値を保持できます。 20バイトを超える購入IDを設定した場合、値は切り捨てられます。

```js
s.purchaseID = "uniqueid";
```
