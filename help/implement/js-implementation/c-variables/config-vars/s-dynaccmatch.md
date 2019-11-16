---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountMatch

 変数は DOM オブジェクトを使用して、 のすべてのルールが適用される URL のセクションを取得します。

この変数は、*`dynamicAccountSelection`* が「True」に設定されているときのみ有効です。デフォルト値は [!DNL window.location.host] であるので、この変数は[!UICONTROL 動的アカウント選択]が動作するための必須の変数ではありません。詳しくは、「[dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)」を参照してください。

`dynamicAccountList` に示すルールは、`dynamicAccountMatch` の値に適用されます。`dynamicAccountMatch` にのみ [!DNL window.location.host] が含まれる場合（デフォルト）、`dynamicAccountList` のルールはページのドメインにのみ適用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | window.location.host |

## 構文と可能な値

`dynamicAccountMatch` 変数は通常、JavaScript 版 AppMeasurement ファイルを提供するアドビコンサルタントによって設定されます。ただし、以下に挙げる値はいつでも適用できます。

```js
s.dynamicAccountMatch=[DOM object]
```

| 説明 | 値 |
|---|---|
| ドメイン（デフォルト） | window.location.host |
| パス | window.location.pathname |
| クエリ文字列 | (window.location.search?window.location.search:"?") |
| ドメインとパス | window.location.host+window.location.pathname |
| パスとクエリ文字列 | window.location.pathname+(window.location.search?window.location.search:"?") |
| 完全修飾 URL | window.location.href |

## 例

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## 設定

なし

## 注意事項、質問、ヒント

* [JavaScript 版 AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)では、動的なアカウント選択はサポ ートされていません。

* ページがハードドライブに保存されている場合、[!DNL window.location.host] は空になり、これらのページビュー数はデフォルトのレポートスイート（`s_account`）.

* ページが Google などの Web ベースの翻訳エンジンによって翻訳されている場合、[!UICONTROL 動的アカウント選択]は設計どおりに動作しません。より精度の高いトラッキングをおこなうには、[!UICONTROL s_account] 変数をサーバーサイドで設定してください。
