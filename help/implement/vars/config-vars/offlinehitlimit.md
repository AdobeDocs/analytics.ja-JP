---
title: offlineHitLimit
description: オフライン追跡用にキューに入れる最大ヒット数を決定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

オフライン追跡は、Adobe Analyticsでデータを収集するオプションの方法です。 訪問者がインターネットから切断したが、引き続きサイトを閲覧した場合、デバイスがインターネットに再接続されるまで、ヒットはオフラインキューに保存されます。 オフライン追跡は、主にモバイルアプリケーションで使用されます。

この変 `offlineHitLimit` 数は、デバイスがローカルに保存するヒット数の上限を設定します。 この変数は、が有効な場合にの [`trackOffline`](trackoffline.md) み機能します。

## Adobe Experience Platform Launchでのオフラインヒットの制限

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.offlineHitLimitとカスタムコードエディターの起動

この変 `s.offlineHitLimit` 数は、オフライン時にデバイスが保存する最大ヒット数を表す整数です。 この変数を定義しない場合、オフライン時にデバイスが保存するヒット数に制限はありません。

```js
s.offlineHitLimit = 100;
```
