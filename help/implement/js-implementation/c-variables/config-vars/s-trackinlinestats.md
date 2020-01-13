---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.trackInlineStats

 変数は、ClickMap データを収集するかどうかを決定します。

*`trackInlineStats`* が「true」の場合、ページおよびクリックされたリンクのデータが、s_sq という cookie に保存されます。false の場合、s_sq には "[[B]]" の値（null と見なされる）がセットされます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | ClickMap | False |

## 構文と可能な値

```
js
s.trackInlineStats=true|false
```

*`trackInlineStats`* 変数には、「true」または「false」を設定する必要があります。

## 例

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## 設定

なし
