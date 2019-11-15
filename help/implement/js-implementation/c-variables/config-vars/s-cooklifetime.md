---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieLifetime

 変数は、JavaScript とデータ収集サーバーの両方で、Cookie の有効期限を決定するために使用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | cl | トラフィック／技術／cookie（訪問者関連のすべてのレポート） | "" |

If *`cookieLifetime`* is set, it overrides any other cookie expirations for both JavaScript and data collection servers, with one exception, described below. *`cookieLifetime`* 変数には以下の 3 つの値のいずれかを設定できます。

* [!DNL Analytics] Cookie
* Cookie
* JavaScript 設定とプラグイン

## 構文と可能な値

```js
s.cookieLifetime="value"
```

有効な値は以下のとおりです。

* ""
* "NONE"
* "SESSION"
* 有効期限が切れるまでの秒数を表す整数

## 例

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## 設定

なし

## 注意事項、質問、ヒント

*`cookieLifetime`* は [!DNL Analytics] トラッキングに影響します。*`cookieLifetime`* が 2日間の場合、月別、四半期別および年別訪問者数レポートに正しい値が表示されません。*`cookieLifetime`* を使用する際は注意してください。
