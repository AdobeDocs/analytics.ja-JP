---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

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

*`trackInlineStats`変数には、「true」または「false」を設定する必要があります。*

## 例

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## 設定

なし
