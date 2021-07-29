---
title: useBeacon
description: useBeacon を使用すると、AppMeasurement で強制的にブラウザーの sendBeacon API を使用できます
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 90%

---

# useBeacon

最新のブラウザーのほとんどに `navigator.sendBeacon()` ネイティブメソッドが含まれています。HTTP 経由で Web サーバーに少量のデータを非同期に送信します。`useBeacon` 変数が有効な場合、AppMeasurement は `navigator.sendBeacon()` メソッドを使用できます。これは、ページがアンロードされる前に情報を送信する出口リンクなどの状況で役立ちます。

`useBeacon` が有効である場合、アドビに送信される次のヒットでは、標準の `GET` イメージリクエストの代わりに、ブラウザーの `navigator.sendBeacon()` メソッドが使用されます。この変数は、[`s.t()`](../functions/t-method.md) と [`s.tl()`](../functions/tl-method.md) の両方のイメージリクエストに適用されます。AppMeasurement 2.17.0 以降が必要です。

>[!TIP]
>
> AppMeasurement は、出口リンクイメージリクエストで `useBeacon` を自動的に有効にします。

訪問者が `useBeacon` をサポートしていないブラウザーを使用している場合、`navigator.sendBeacon()` 変数は無視されます。この変数を使用するには、AppMeasurement 2.16.0 以降が必要です。

## Adobe Experience Platformのタグを使用したビーコンの使用

データ収集UIには、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.useBeacon

`s.useBeacon` 変数は、AppMeasurement がブラウザーの `navigator.sendBeacon()` メソッドを使用するかどうかを決定するブール値です。デフォルト値は `false` です。`navigator.sendBeacon()` の非同期性を使用する場合は、トラッキング関数を呼び出す前にこの変数を `true` に設定します。

```js
s.useBeacon = true;
```

>[!NOTE]
>
> トラッキングコールの実行後、この変数は `false` にリセットされます。実装が同じページ読み込みで複数のイメージリクエストを送信する場合（単一ページのアプリケーションなど）、各トラッキングコールの前にこの変数を `true` に設定します。
