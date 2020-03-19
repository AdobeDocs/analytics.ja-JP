---
title: 購入イベント
description: 購入イベントを使用して、「注文件数」、「数量」、「売上高」の各指標のデータを収集します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 購入イベント

購入イベントは変数内の値 `events` です。 この値は、サイトが生み出す売上高に関するデータを収集する組織で役立ちます。 変数と変数に大きく依存 [`products`](../products.md) してい [`purchaseID`](../purchaseid.md) ます。

購入イベントを設定すると、次の指標に影響します。

* 「注文件数」指標は1増分されます
* 「数量」指標は、変数内の製品数だけ増分されま `products` す
* 「売上高」指標は、変数内の価格パラメーターの合計によって増加しま `products` す

## Adobe Experience Platform Launchでの購入イベントの設定

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. セクションを [!UICONTROL Events] 見つけ、イベントドロップダウンをに設定しま [!UICONTROL purchase]す。

とのような他の依存変数は、起動 `products` 時に `purchaseID` 専用フィールドを持ちません。 これらの変数に対して、AppMeasurement構文に従ったカスタムコードエディターを使用します。

## AppMeasurementで購入イベントを設定し、カスタムコードエディターを起動

購入イベントは、イベント変数の一部として設定される文字列です。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 購入イベントの重複除外

購入イベントを発生させると、アドビは次の項目を確認します。

* ヒットに変数が含まれてい `purchaseID` るか。 そうでない場合、アドビはヒットの情報を使用して「一時的な購入ID」を作成します。 この一時的な購入 ID は、ヒットの訪問者にのみ適用されます。以前の5つの一時的な購入IDは、レポートスイートごとに各訪問者IDに対して保存されます。
* 一時的な購入IDは、保存されている直近5つの一時的な購入IDのいずれかと一致しますか。 一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
* 変数が定義さ `purchaseID` れている場合、すべての訪問者で既にレポートスイートで収集されている値と一致しますか。 一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
