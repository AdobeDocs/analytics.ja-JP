---
title: offlineHitLimit
description: オフライン追跡用にキューに入れる最大ヒット数を決定します。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# offlineHitLimit

オフライン追跡は、Adobe Analyticsでデータを収集するオプションの方法です。 訪問者がインターネットから切断したが、引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。 オフライン追跡は、ほとんどの場合モバイルアプリケーションで使用されます。

この変 `offlineHitLimit` 数は、デバイスがローカルに保存するヒット数に上限を設定します。 この変数は、がの場合にのみ機 `trackOffline` 能しま `true`す。

## Adobe Experience Platform Launchでのオフラインヒットの制限

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.offlineHitLimitおよびカスタムコードエディターの起動

この変 `s.offlineHitLimit` 数は、オフライン時にデバイスが保存する最大ヒット数を表す整数です。 この変数を定義しない場合、オフライン時にデバイスが保存するヒット数に制限はありません。

```js
s.offlineHitLimit = 100;
```
