---
title: useBeacon
description: useBeaconを使用すると、AppMeasurementで強制的にブラウザsendBeacon APIを使用できます
keywords: Analytics Implementation
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# s.useBeacon

この変 `s.useBeacon` 数は、次のリクエストに強制的にブラウザーのsendBeacon APIを使 [用させます](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)。 を使用す `s.sendBeacon` ると、ページのコンテキスト外でHTTPリクエストを送信できます。 ページがアンロードされる前に情報を送信する離脱リンクなどの状況で役立ちます。

この値の設定は、AppMeasurementが実行される次のリクエストにのみ適用されます。 リクエストが実行された後、 `s.useBeacon` falseにリセットされます。 この変数は、とイメージリクエストの `s.t()` 両方に `s.tl()` 適用されます。

この変数を `s.useBeacon` 使用するには、AppMeasurement 2.17.0以降が必要です。

> [!NOTE] 離脱リ [ンクは](s-linktrackvars.md) 、この変数を追加の設定なしで自動的に使用します。

## 構文

```js
s.useBeacon = true;
```
