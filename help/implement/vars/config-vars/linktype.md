---
title: linkType
description: linkType 変数は、ヒットが属するリンクトラッキングディメンションを特定するのに使用します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkType

リンクトラッキングのヒットには、次の 3 つのディメンションのいずれかを設定できます。

* カスタムリンク
* 出口リンク
* ダウンロードリンク

`linkType` 変数を使用して、次の [`tl()`](../functions/tl-method.md) 関数の実行時に入力するディメンションを決定します。

## Adobe Experience Platform Launch の「リンクタイプ」

ビーコンを送信するルールを設定する場合は、リンクタイプを設定します。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Type] dropdown.

このドロップダウンは、、、また [!UICONTROL Custom Link]はのいず [!UICONTROL Download Link]れかに設定できま [!UICONTROL Exit Link]す。

## AppMeasurement および Launch カスタムコードエディターの s.linkType

`s.linkType` 変数は、`o`、`d`、`e` の 3 つの 1 文字の値のいずれかを受け取る文字列です。If a `tl()` method is called without a link type, it defaults to Custom link.

* `o` - カスタムリンク
* `d` - ダウンロードリンク
* `e` - 出口リンク

>[!TIP] この変数はメソッドの2番目のパラメー `tl()` ターで、通常、スタンドアロン変数として設定する必要はありません。 However, you can use the `linkType` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkType = "e";
```

## 例

次の 2 つのリンクトラッキングコールの例は、機能的に同じです。同じリンクトラッキングヒットを達成するには、異なる方法があります。

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
