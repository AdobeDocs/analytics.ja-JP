---
title: offlineThrottleDelay
description: デバイスがオンラインに戻ったときのヒットの頻度を設定します。
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

オフライン追跡は、Adobe Analyticsでデータを収集するオプションの方法です。 訪問者がインターネットから切断したが、引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。 オフライン追跡は、ほとんどの場合モバイルアプリケーションで使用されます。

デバイスがオンラインに戻ると、デバイスに保存されているすべてのヒットがアドビのデータ収集サーバーに送信されます。 キューに格納されたヒットの数が多いと、古いデバイスのパフォーマンスに影響を与える可能性があります。 この変数を使 `offlineThrottleDelay` 用して、キューに登録されたヒットがアドビに送信される頻度を指定します。

## Adobe Experience Platform Launchでのオフラインスロットル遅延

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.offlineThrottleDelayとカスタムコードエディターの起動

この変 `s.offlineThrottleDelay` 数は、キューに格納されたヒットを送信する間にAppMeasurementが待機するミリ秒数を表す整数です。 デフォルト値はです。つまり、キ `0`ューに登録されているすべてのヒットが一度に送信されます。 が含まれ `trackOffline` ている場 `false`合、この変数は何もしません。

```js
s.offlineThrottleDelay = 500;
```
