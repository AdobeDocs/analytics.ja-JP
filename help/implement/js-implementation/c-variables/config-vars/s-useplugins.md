---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.usePlugins

関数が利用可能になっていて、有効なコードが含まれている場合は、[!UICONTROL s_usePlugins] を「true」に設定する必要があります。

[!UICONTROL usePlugins] が「true」の場合、イメージリクエストの前に *`s_doPlugins`* 関数が呼び出されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

## 構文と可能な値

```js
s.usePlugins=true|false
```

[!UICONTROL usePlugins] 変数には、「true」または「false」を設定する必要があります。

## 例

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

JavaScript ファイル内で *`s_doPlugins`* 関数が宣言されていない場合、[!UICONTROL usePlugins] 関数は false （または宣言なし）になります。

## 設定

なし
