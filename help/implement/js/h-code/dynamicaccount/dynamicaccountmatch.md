---
title: dynamicAccountMatch
description: dynamicAccountMatch 変数は、動的アカウントで表示する値を決定します。
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: ht
source-wordcount: '127'
ht-degree: 100%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
> 動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。これらの変数は、現在の AppMeasurement ライブラリや Adobe Experience Platform のタグではサポートされていません。

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
