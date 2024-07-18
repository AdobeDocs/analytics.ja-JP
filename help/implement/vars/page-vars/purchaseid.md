---
title: purchaseID
description: 一意の購入識別子に基づいてヒットの重複を除外します。
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 4bd46fd5a9b98bcca67a66c87c9bca67fa00061a
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 73%

---

# purchaseID

`purchaseID` 変数は、同じ購入を含むヒットによるレポートの水増しを防ぐのに役立ちます。例えば、訪問者が購入確認ページに到達した場合、通常はトランザクションから生み出された売上高に関するデータをアドビに送信します。ユーザーがこのページを複数回更新したり、後で訪問するページをブックマークしたりした場合、これらのヒットによってレポートが水増しされる可能性があります。複数のヒットに同じ購入 ID がある場合、`purchaseID` 変数は指標の重複を排除します。

アドビがヒットを重複購入と認識した場合、すべてのコンバージョンデータ（eVar やイベントなど）はレポートに表示されません。データフィードでは、`duplicate_purchase` 列は `1` に設定されます。

購入 ID はすべての訪問者に適用され、37 か月後に有効期限が切れます。 ある訪問者が特定の購入 ID を設定し、その 1 年後に同じ購入 ID を別の訪問者が設定した場合、2 番目の購入の重複が排除されます。

## Web SDK を使用した購入 ID

購入 ID は、次の変数にマッピングされます。

* [XDM オブジェクト ](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.purchaseID`
* [ データ オブジェクト ](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.purchaseID`

## Adobe Analytics拡張機能を使用した購入 ID

購入 ID は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL  拡張機能 ]」ドロップダウンリストをAdobe Analyticsに設定し、「[!UICONTROL  アクションタイプ ]」を [!UICONTROL  変数を設定 ] に設定します。
6. 「[!UICONTROL  購入 ID]」セクションを見つけます。

購入 ID は値またはデータ要素に設定できます。 別の Analytics 変数から値をコピーすることもできます。

## AppMeasurementの s.purchaseID と Analytics 拡張機能のカスタムコードエディター

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
