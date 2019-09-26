---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieLifetime

 変数は、JavaScript とデータ収集サーバーの両方で、Cookie の有効期限を決定するために使用されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | cl | トラフィック／技術／cookie（訪問者関連のすべてのレポート） | "" |

if *`cookieLifetime`* が設定されている場合、JavaScript とデータ収集サーバーの両方について、その値が他のすべての cookie 有効期限よりも優先されますが、以下で説明するように 1 つだけ例外があります。The *`cookieLifetime`* variable can have one of three values:

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

*`cookieLifetime`* affects  tracking. [!DNL Analytics]If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Use caution when setting *`cookieLifetime`*.
