---
title: useBeacon
description: useBeacon を使用すると、AppMeasurement で強制的にブラウザーの sendBeacon API を使用できます
keywords: Analytics Implementation
translation-type: ht
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# s.useBeacon

`s.useBeacon` 変数は、次のリクエストに強制的にブラウザーの [sendBeacon API](https://developer.mozilla.org/ja-JP/docs/Web/API/Navigator/sendBeacon) を使用させます。`s.sendBeacon` を使用すると、ページのコンテキスト外で HTTP リクエストを送信できます。ページがアンロードされる前に情報を送信する出口リンクなどの状況で役立ちます。

この値の設定は、AppMeasurement が実行される次のリクエストにのみ適用されます。リクエストが実行された後、`s.useBeacon` が false にリセットされます。この変数は、`s.t()` と `s.tl()` の両方のイメージリクエストに適用されます。

`s.useBeacon` 変数を使用するには、AppMeasurement 2.17.0 以降が必要です。

> [!NOTE] [出口リンク](s-linktrackvars.md)は、この変数を追加の設定なしで自動的に使用します。

## 構文

```js
s.useBeacon = true;
```
