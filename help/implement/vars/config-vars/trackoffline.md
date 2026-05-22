---
title: trackOffline
description: オフライントラッキングを有効または無効にします。これにより、AppMeasurement でのデータ収集方法が変更されます。
feature: Appmeasurement Implementation
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/6VDAO0-QMXqia2Ddy1uPcxnTrlJi49B8zjaLcC0HawU'
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
source-wordcount: 283
ht-degree: 89%

---

# trackOffline

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。 訪問者がインターネットから切断したが引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。 オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

`trackOffline` 変数は、実装でオフライントラッキングを使用するかどうかを決定します。

>[!WARNING]
>
>この変数を有効にする前に、タイムスタンプ付きのヒットを受け入れるようにレポートスイートを設定する必要があります。 レポートスイートでタイムスタンプ付きのヒットが受け入れられず、この変数が有効な場合、そのデータは失われ、復元できません。

有効にすると、AppMeasurement は次のプロセスを使用してアドビにデータを送信します。

* イメージリクエストをコンパイルする際に、タイムスタンプクエリ文字列パラメーターが含まれます。
* デバイスがアドビのデータ収集サーバーに接続できない場合、ヒットはデバイスにローカルに保存されます。
* 後続のヒットのたびに、AppMeasurement はイメージリクエストをアドビに送信しようとします。
   * アドビのデータ収集サーバーに接続できない場合、ヒットはデバイス上のキューに追加されます。
   * アドビのデータ収集サーバーに接続できる場合は、デバイスがオフラインの間のヒットおよびヒットのキューが送信されます。

## Web SDKを使用したオフライントラッキング

Web SDKはオフライントラッキングをサポートしていません。

## Adobe Analytics拡張機能を使用したオフライントラッキング

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.trackOfflineとAnalytics拡張機能のカスタムコードエディター

`s.trackOffline` 変数は、オフライントラッキングを有効または無効にするブール値です。 デフォルト値は `false` です。 オフライントラッキングを有効にする場合は、この値を `true` に設定します。

```js
s.trackOffline = true;
```
