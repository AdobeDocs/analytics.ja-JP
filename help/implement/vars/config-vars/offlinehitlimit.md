---
title: offlineHitLimit
description: オフライントラッキング用にキューに入れる最大ヒット数を決定します。
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 79%

---

# offlineHitLimit

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。訪問者がインターネットから切断したが引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

`offlineHitLimit` 変数は、デバイスがローカルに保存するヒット数に上限を設定します。この変数は、[`trackOffline`](trackoffline.md) が有効な場合にのみ機能します。

## Adobe Analytics拡張機能を使用したオフラインヒット制限

Adobe Analytics拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.offlineHitLimit

`s.offlineHitLimit` 変数は、オフライン時にデバイスが保存する最大ヒット数を表す整数です。この変数を定義しない場合、オフライン時にデバイスが保存するヒット数に制限はありません。

```js
s.offlineHitLimit = 100;
```
