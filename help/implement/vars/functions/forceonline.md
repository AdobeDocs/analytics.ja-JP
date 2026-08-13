---
title: forceOnline
description: AppMeasurement のオンライン状態を手動で設定します。
feature: Appmeasurement Implementation
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/qPSlGDmNTccOtGRvlu-xr-wf1hV18OA-yyiuScnZr7g'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 157
ht-degree: 80%

---

# forceOnline

`forceOnline()` メソッドを使用すると、自動的に検出された AppMeasurement の状態を上書きできます。

>[!WARNING]
>
>このメソッドは、[`trackOffline`](../config-vars/trackoffline.md) が有効な場合にのみ使用します。 この関数をオフライントラッキング以外で使用すると、データが失われる可能性があります。

AppMeasurement は、デバイスのオンライン状態を自動的に検出します。 `forceOnline()` メソッドを使用すると、AppMeasurement がデバイスがオンラインの場合と同様にヒットを処理するように強制できます。 このメソッドは引数を取らず、値を返しません。 AppMeasurement でオンライン状態を上書きするのが目的です。

## Web SDKを使用して強制的にオンラインにする

Web SDKはオフライントラッキングをサポートしていません。

## Adobe Analytics拡張機能を使用して強制的にオンラインにする

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.forceOnline （）とAnalytics拡張機能のカスタムコードエディター

Analytics オブジェクトをインスタンス化した後、実装の任意の場所で `s.forceOnline()` メソッドを呼び出すことができます。

```js
s.forceOnline();
```
