---
title: purchaseID
description: 一意の購入識別子に基づいてヒットの重複を除外します。
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '254'
ht-degree: 100%

---

# purchaseID

`purchaseID` 変数は、同じ購入を含むヒットによるレポートの水増しを防ぐのに役立ちます。例えば、訪問者が購入確認ページに到達した場合、通常はトランザクションから生み出された売上高に関するデータをアドビに送信します。ユーザーがこのページを複数回更新したり、後で訪問するページをブックマークしたりした場合、これらのヒットによってレポートが水増しされる可能性があります。複数のヒットに同じ購入 ID がある場合、`purchaseID` 変数は指標の重複を排除します。

アドビがヒットを重複購入と認識した場合、すべてのコンバージョンデータ（eVar やイベントなど）はレポートに表示されません。データフィードでは、`duplicate_purchase` 列は `1` に設定されます。

購入 ID はすべての訪問者に適用され、期限は切れません。ある訪問者が特定の購入 ID を設定し、その 1 年後に同じ購入 ID を別の訪問者が設定した場合、2 番目の購入の重複が排除されます。

## Adobe Experience Platform Launch での購入 ID

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.purchaseID

`s.purchaseID` 変数は、購入に対する一意の ID を含む文字列です。これは購入イベントと同じヒットに設定されます。この変数を設定するには、英数字のみを使用します。

この変数には最大 20 バイトを格納できます。20 バイトを超える値は切り捨てられます。この切り捨てられた値が後続の切り捨てられた値と一致する場合、後続のヒットの重複は排除されます。

```js
s.purchaseID = "ABC123";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
> 購入 ID の生成にランダム化関数を使用しないでください。
