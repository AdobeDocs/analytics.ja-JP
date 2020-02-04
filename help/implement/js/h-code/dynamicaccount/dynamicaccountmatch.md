---
title: dynamicAccountMatch
description: dynamicAccountMatch変数は、動的アカウントで表示する値を決定します。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] 動的アカウントは、レガシーJavaScript実装（Hコード）を使用した場合にのみサポートされます。 これらの変数は、現在のAppMeasurementライブラリまたはAdobe Experience Platform Launchではサポートされていません。

変 `dynamicAccountMatch` 数は、値を調べ `dynamicAccountList` て比較する値です。 をに設 `dynamicAccountSelection` 定しない場合、こ `true`の変数は無視されます。

この変数を定義しない場合、デフォルト値はです `window.location.host`。

## 構文

```js
s.dynamicAccountMatch=[DOM object]
```

## 例

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## 追加情報

* ハードドライブに保存されたページには、複数の変数が定義 `location` されていません(例えば、空白 `location.host` の場合)。 デフォルトのレポ `s_account` ートスイートが含まれていることを確認します。
* ページがGoogleなどのWebベースの翻訳エンジンを介して翻訳される場合、動的アカウント選択は設計のとおりに機能しません。 For more precise tracking, populate the `s_account` variable server-side.
