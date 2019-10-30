---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.dynamicAccountSelection

 変数を使用すると、各ページの URL に基づきレポートスイートを動的に選択できます。

> [!NOTE]`dynamicAccountSelection` はカスタムリンクトラッキングでは動作しません。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | False |

> [!NOTE]`dynamicAccountList` と `dynamicAccountMatch` の両方は、`dynamicAccountSelection` 変数が宣言されていないか「False」に設定されている場合、無視されます。

## 構文と可能な値

```js
s.dynamicAccountSelection=[true|false]
```

*`dynamicAccountSelection`* の値には、「true」と「false」のみを使用できます。

## 例

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## 設定

なし

## 注意事項、質問、ヒント

* [JavaScript 版 AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)では、動的なアカウント選択はサポ ートされていません。

* 各ページからデータを受信するレポートスイートを決定する場合は、必ず [!DNL DigitalPulse Debugger] を使用してください。
