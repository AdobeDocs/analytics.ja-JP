---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.usePlugins

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

usePlugins [!UICONTROL が「true] 」の場合、各イメージリクエ *`s_doPlugins`* ストの前に関数が呼び出されます。

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

[!UICONTROL usePlugins] 変数を false に設定する（またはこの変数を宣言しない）のは、 *`s_doPlugins`* function is not declared in your JavaScript file.

## 設定

なし