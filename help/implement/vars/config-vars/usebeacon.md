---
title: useBeacon
description: useBeacon を使用すると、AppMeasurement で強制的にブラウザーの sendBeacon API を使用できます
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# useBeacon

最新のブラウザーのほとんどにネイティブメソッドが含まれていま `navigator.sendBeacon()`す。 HTTP経由でWebサーバーに少量のデータを非同期に送信します。 変数が有効な場合、AppMeasurement `navigator.sendBeacon()` はこのメソッド `useBeacon` を使用できます。 ページがアンロードされる前に情報を送信する離脱リンクなどの状況で役立ちます。

が有効 `useBeacon` な場合、アドビに送信される次のヒットでは、標準のイメージリクエストではなく、ブ `navigator.sendBeacon()` ラウザーの方法が使用 `GET` されます。 この変数は、`s.t()` と `s.tl()` の両方のイメージリクエストに適用されます。AppMeasurement 2.17.0以降が必要です。

> [!TIP] AppMeasurementは、離脱リンクイメージ `useBeacon` リクエストを自動的に有効にします。

訪問者 `useBeacon` がサポートしないブラウザーを使用する場合、この変数は無視されま `navigator.sendBeacon()`す。

## Adobe Experience Platform Launchでのビーコンの使用

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.useBeaconとカスタムコードエディターの起動

この変 `s.useBeacon` 数は、AppMeasurementがブラウザーのメソッドを使用するかどうかを決定するブール値 `navigator.sendBeacon()` です。 Its default value is `false`. の非同期性を使用する `true` 場合は、トラッキング関数を呼び出す前にこの変数をに設定しま `navigator.sendBeacon()`す。

```js
s.useBeacon = true;
```

> [!NOTE] トラッキングコールの実行後、この変数はにリセットされま `false`す。 実装が同じページ読み込みで複数のイメージリクエストを送信する場合（単一ページのアプリケーションなど）、各トラッキングコールの前にこの変 `true` 数をに設定します。
