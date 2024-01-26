---
title: offlineHitLimit
description: オフライントラッキング用にキューに入れる最大ヒット数を決定します。
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 88%

---

# offlineHitLimit

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。訪問者がインターネットから切断したが引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

`offlineHitLimit` 変数は、デバイスがローカルに保存するヒット数に上限を設定します。この変数は、[`trackOffline`](trackoffline.md) が有効な場合にのみ機能します。

## Adobe Analytics拡張機能を使用したオフラインヒット制限

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.offlineHitLimit

`s.offlineHitLimit` 変数は、オフライン時にデバイスが保存する最大ヒット数を表す整数です。この変数を定義しない場合、オフライン時にデバイスが保存するヒット数に制限はありません。

```js
s.offlineHitLimit = 100;
```
