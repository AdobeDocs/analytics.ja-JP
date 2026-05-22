---
title: offlineThrottleDelay
description: デバイスがオンラインに戻ったときのヒットの頻度を設定します。
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/FiC4yXkRmNoY0PPO9ouC8-hX5xqWhkbcDVht5f05Yqk'
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
source-wordcount: 195
ht-degree: 83%

---

# offlineThrottleDelay

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。 訪問者がインターネットから切断したが引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。 オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

デバイスが再びオンラインになると、デバイスに保存されているすべてのヒットがアドビのデータ収集サーバーに送信されます。 キューに格納されたヒットの数が多いと、古いデバイスのパフォーマンスに影響を与える可能性があります。 `offlineThrottleDelay` 変数を使用して、キューに登録されたヒットがアドビに送信される頻度を指定します。

## Web SDKを使用したオフラインスロットル遅延

Web SDKはオフライントラッキングをサポートしていません。

## Adobe Analytics拡張機能を使用したオフラインスロットル遅延

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.offlineThrottleDelayとAnalytics拡張機能のカスタムコードエディター

`s.offlineThrottleDelay` 変数は、キューに格納されたヒットを送信する間に AppMeasurement が待機するミリ秒数を表す整数です。 デフォルト値は `0` です。つまり、キューに登録されているすべてのヒットが一度に送信されます。 `trackOffline` が `false` である場合、この変数は何もしません。

```js
s.offlineThrottleDelay = 500;
```
