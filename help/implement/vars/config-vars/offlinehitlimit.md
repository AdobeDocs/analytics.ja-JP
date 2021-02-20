---
title: offlineHitLimit
description: オフライントラッキング用にキューに入れる最大ヒット数を決定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 100%

---


# offlineHitLimit

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。訪問者がインターネットから切断したが引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

`offlineHitLimit` 変数は、デバイスがローカルに保存するヒット数に上限を設定します。この変数は、[`trackOffline`](trackoffline.md) が有効な場合にのみ機能します。

## Adobe Experience Platform Launch でのオフラインヒット数の上限

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.offlineHitLimit

`s.offlineHitLimit` 変数は、オフライン時にデバイスが保存する最大ヒット数を表す整数です。この変数を定義しない場合、オフライン時にデバイスが保存するヒット数に制限はありません。

```js
s.offlineHitLimit = 100;
```
