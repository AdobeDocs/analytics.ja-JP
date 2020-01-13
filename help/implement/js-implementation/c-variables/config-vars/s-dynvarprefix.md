---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

 変数を使用すると、動的に設定する必要のある変数にフラグを付けることができます。

動的に設定できるものには、cookie、リクエストのヘッダーおよびイメージクエリ文字列パラメーターがあります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | D= | いずれか | D= |

## 構文と可能な値

```js
s.prop1="D=User-Agent"
```

または、動的変数用のカスタムフラグを使用します。

```js
s.dynamicVariablePrefix=".."
```

## 例

```js
s.prop1="D=User-Agent"
```

または、動的変数用のカスタムフラグを使用します。

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## 注意事項、質問、ヒント

* 動的変数は、値を他の変数にコピーすることで、URL の全体的な長さを大幅に短縮するために使用できます。

* 動的変数は、データ収集では通常取得されないようなヘッダーおよび cookie からデータを収集するために使用できます。
