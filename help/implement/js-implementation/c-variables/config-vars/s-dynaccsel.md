---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountSelection

 変数を使用すると、各ページの URL に基づきレポートスイートを動的に選択できます。

>[!NOTE]
>
>`dynamicAccountSelection` はカスタムリンクトラッキングでは動作しません。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

## 構文と可能な値

```js
s.dynamicAccountSelection=[true|false]
```

「true」と「false」のみを *`dynamicAccountSelection`*（名前をつけて保存）する必要があります。

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

* 動的なアカウント選択は、 [JavaScript 版 AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* 各ページからデータを受信するレポートスイートを決定する場合は、必ず [!DNL DigitalPulse Debugger] を使用してください。
