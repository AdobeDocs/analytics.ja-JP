---
title: offlineHitLimit
description: オフライントラッキング用にキューに入れる最大ヒット数を決定します。
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '158'
ht-degree: 100%

---

# offlineHitLimit

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。訪問者がインターネットから切断したが引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

`offlineHitLimit` 変数は、デバイスがローカルに保存するヒット数に上限を設定します。この変数は、[`trackOffline`](trackoffline.md) が有効な場合にのみ機能します。

## Adobe Experience Platform のタグを使用したオフラインヒットの制限

データ収集 UI には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.offlineHitLimit

`s.offlineHitLimit` 変数は、オフライン時にデバイスが保存する最大ヒット数を表す整数です。この変数を定義しない場合、オフライン時にデバイスが保存するヒット数に制限はありません。

```js
s.offlineHitLimit = 100;
```
