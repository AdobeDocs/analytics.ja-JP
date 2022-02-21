---
title: offlineThrottleDelay
description: デバイスがオンラインに戻ったときのヒットの頻度を設定します。
feature: Variables
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 100%

---

# offlineThrottleDelay

オフライントラッキングは、Adobe Analytics でデータを収集するオプションの方法です。訪問者がインターネットから切断したが引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。オフライントラッキングは、ほとんどの場合モバイルアプリケーションで使用されます。

デバイスが再びオンラインになると、デバイスに保存されているすべてのヒットがアドビのデータ収集サーバーに送信されます。キューに格納されたヒットの数が多いと、古いデバイスのパフォーマンスに影響を与える可能性があります。`offlineThrottleDelay` 変数を使用して、キューに登録されたヒットがアドビに送信される頻度を指定します。

## Adobe Experience Platform のタグを使用したオフラインスロットル遅延

データ収集 UI には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.offlineThrottleDelay

`s.offlineThrottleDelay` 変数は、キューに格納されたヒットを送信する間に AppMeasurement が待機するミリ秒数を表す整数です。デフォルト値は `0` です。つまり、キューに登録されているすべてのヒットが一度に送信されます。`trackOffline` が `false` である場合、この変数は何もしません。

```js
s.offlineThrottleDelay = 500;
```
