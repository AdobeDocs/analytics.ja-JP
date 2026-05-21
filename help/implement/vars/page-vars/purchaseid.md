---
title: purchaseID
description: 一意の購入識別子に基づいてヒットの重複を除外します。
feature: Appmeasurement Implementation
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
TQID: https://experienceleague.adobe.com/A8QIQQbtDhZcQmnokBcQdMqJVAbu1PD7N363QdHcSJc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 369
ht-degree: 78%

---

# purchaseID

`purchaseID` 変数は、同じ購入を含むヒットによるレポートの水増しを防ぐのに役立ちます。 例えば、訪問者が購入確認ページに到達した場合、通常はトランザクションから生み出された売上高に関するデータをアドビに送信します。 ユーザーがこのページを複数回更新したり、後で訪問するページをブックマークしたりした場合、これらのヒットによってレポートが水増しされる可能性があります。 複数のヒットに同じ購入 ID がある場合、`purchaseID` 変数は指標の重複を排除します。

アドビがヒットを重複購入と認識した場合、すべてのコンバージョンデータ（eVar やイベントなど）はレポートに表示されません。 データフィードでは、`duplicate_purchase` 列は `1` に設定されます。

購入IDはすべての訪問者に適用され、37か月後に期限切れになります。 ある訪問者が特定の購入 ID を設定し、その 1 年後に同じ購入 ID を別の訪問者が設定した場合、2 番目の購入の重複が排除されます。

## Web SDKを使用した購入ID

購入IDは、次の変数にマッピングされます。

* [XDM オブジェクト ](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.purchaseID`
* [ データオブジェクト ](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.purchaseID`

## Adobe Analytics拡張機能を使用した購入ID

購入IDは、Analytics拡張機能（グローバル変数）の設定中またはルールの下に設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. [!UICONTROL 購入ID] セクションを探します。

購入IDには、値またはデータ要素を設定できます。 別の Analytics 変数から値をコピーすることもできます。

## AppMeasurementのs.purchaseIDとAnalytics拡張機能のカスタムコードエディター

`s.purchaseID` 変数は、購入に対する一意の ID を含む文字列です。 これは購入イベントと同じヒットに設定されます。 この変数を設定するには、英数字のみを使用します。

この変数には最大 20 バイトを格納できます。20 バイトを超える値は切り捨てられます。 この切り捨てられた値が後続の切り捨てられた値と一致する場合、後続のヒットの重複は排除されます。

```js
s.purchaseID = "ABC123";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>購入 ID の生成にランダム化関数を使用しないでください。
