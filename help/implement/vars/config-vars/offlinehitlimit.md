---
title: offlineHitLimit
description: オフライントラッキング用にキューに入れる最大ヒット数を決定します。
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 8bc5e649c5b5852232f4baddcddad0766bc1569a
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 39%

---

# offlineHitLimit

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。訪問者がインターネットから切断してもサイトを引き続き参照すると、ヒットは、デバイスがインターネットに再接続するまで、オフラインキューに格納されます。 オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

`offlineHitLimit` 変数は、デバイスがローカルに保存するヒット数に上限を設定します。この変数は、[`trackOffline`](trackoffline.md) が有効な場合にのみ機能します。

## Web SDK を使用したオフラインヒットの制限

Web SDK はオフライントラッキングをサポートしていません。

## Adobe Analytics拡張機能を使用したオフラインヒットの制限

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementーおよび Analytics 拡張機能のカスタムコードエディターの s.offlineHitLimit

この `s.offlineHitLimit` 変数は、オフライン時にデバイスが保存するヒットの最大数を表す整数です。 この変数が定義されていない場合は、デフォルトで `10`. 任意の整数値に設定できます。 高い値を設定する場合は、訪問者のブラウザーのローカルストレージ上限に注意してください。 この制限は通常 5～10 MB です。

```js
s.offlineHitLimit = 100;
```
