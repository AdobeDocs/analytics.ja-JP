---
title: offlineHitLimit
description: オフライントラッキング用にキューに入れる最大ヒット数を決定します。
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-uvCAqUO0A-7XjlemN4XwHXVG9DFK-UoVTW77up9-AY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 39%

---

# offlineHitLimit

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。 訪問者がインターネットから切断してもサイトの閲覧を続けた場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。 オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

`offlineHitLimit` 変数は、デバイスがローカルに保存するヒット数にキャップを設定します。 この変数は、[`trackOffline`](trackoffline.md) が有効な場合にのみ機能します。

## Web SDKを使用したオフラインヒット制限

Web SDKはオフライントラッキングをサポートしていません。

## Adobe Analytics拡張機能を使用したオフラインヒット制限

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.offlineHitLimitとAnalytics拡張機能のカスタムコードエディター

`s.offlineHitLimit`変数は、デバイスがオフライン中に保存する最大ヒット数を表す整数です。 この変数が定義されていない場合、デフォルトは`10`になります。 任意の整数値に設定できます。 高い値を設定する場合は、訪問者のブラウザーのローカルストレージの上限に注意してください。 この制限は通常5 ～ 10 MBです。

```js
s.offlineHitLimit = 100;
```
