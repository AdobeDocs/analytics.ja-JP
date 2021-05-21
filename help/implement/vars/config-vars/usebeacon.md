---
title: useBeacon
description: useBeacon を使用すると、AppMeasurement で強制的にブラウザーの sendBeacon API を使用できます
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '229'
ht-degree: 100%

---

# useBeacon

最新のブラウザーのほとんどに `navigator.sendBeacon()` ネイティブメソッドが含まれています。HTTP 経由で Web サーバーに少量のデータを非同期に送信します。`useBeacon` 変数が有効な場合、AppMeasurement は `navigator.sendBeacon()` メソッドを使用できます。これは、ページがアンロードされる前に情報を送信する出口リンクなどの状況で役立ちます。

`useBeacon` が有効である場合、アドビに送信される次のヒットでは、標準の `GET` イメージリクエストの代わりに、ブラウザーの `navigator.sendBeacon()` メソッドが使用されます。この変数は、[`s.t()`](../functions/t-method.md) と [`s.tl()`](../functions/tl-method.md) の両方のイメージリクエストに適用されます。AppMeasurement 2.17.0 以降が必要です。

>[!TIP]
>
> AppMeasurement は、出口リンクイメージリクエストで `useBeacon` を自動的に有効にします。

訪問者が `useBeacon` をサポートしていないブラウザーを使用している場合、`navigator.sendBeacon()` 変数は無視されます。この変数を使用するには、AppMeasurement 2.16.0 以降が必要です。

## Adobe Experience Platform Launch でのビーコンの使用

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.useBeacon

`s.useBeacon` 変数は、AppMeasurement がブラウザーの `navigator.sendBeacon()` メソッドを使用するかどうかを決定するブール値です。デフォルト値は `false` です。`navigator.sendBeacon()` の非同期性を使用する場合は、トラッキング関数を呼び出す前にこの変数を `true` に設定します。

```js
s.useBeacon = true;
```

>[!NOTE]
>
> トラッキングコールの実行後、この変数は `false` にリセットされます。実装が同じページ読み込みで複数のイメージリクエストを送信する場合（単一ページのアプリケーションなど）、各トラッキングコールの前にこの変数を `true` に設定します。
