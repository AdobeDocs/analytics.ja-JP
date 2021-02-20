---
title: dynamicAccountMatch
description: dynamicAccountMatch 変数は、動的アカウントで表示する値を決定します。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 100%

---


# dynamicAccountMatch

>[!IMPORTANT]
>
> 動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。これらの変数は、現在の AppMeasurement ライブラリや Adobe Experience Platform Launch ではサポートされていません。

`dynamicAccountMatch` 変数は、`dynamicAccountList` が値を調べて比較する値です。`dynamicAccountSelection` を `true` に設定しない場合、この変数は無視されます。

この変数を定義しない場合、デフォルト値は `window.location.host` です。

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

* ハードドライブに保存されたページには、複数の `location` 変数が定義されていません（例えば、`location.host` は空白）。`s_account` にデフォルトのレポートスイートが含まれていることを確認します。
* ページが Google などの Web ベースの翻訳エンジンによって翻訳されている場合、動的アカウント選択は設計どおりに動作しません。より精度の高いトラッキングをおこなうには、`s_account` 変数をサーバーサイドで設定してください。
