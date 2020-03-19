---
title: linkType
description: linkType変数を使用して、ヒットが属するリンクトラッキングディメンションを特定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkType

リンクトラッキングのヒットには、次の3つのディメンションのいずれかが含まれます。

* カスタムリンク
* 離脱リンク
* ダウンロードリンク

変数を使 `linkType` 用して、次の関数の実行時に入力するディメンションを決定し [`tl()`](../functions/tl-method.md) ます。

## Adobe Experience Platform Launchのリンクタイプ

ビーコンを送信するルールを設定する場合は、リンクタイプを設定します。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. 下の「 [!UICONTROL Actions]+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、「ビーコンの送 [!UICONTROL Action Type] 信」に設定します。
6. ラジオボタンをク `s.tl()` リックすると、ドロップダウンが表示 [!UICONTROL Link Type] されます。

このドロップダウンは、、、また [!UICONTROL Custom Link]はのいず [!UICONTROL Download Link]れかに設定できま [!UICONTROL Exit Link]す。

## AppMeasurementのs.linkTypeとカスタムコードエディターの起動

変数 `s.linkType` は、次の3つの1文字の値のいずれかを受け取る文字列です。 `o`、ま `d`たは `e`。 リンクタイプを `tl()` 指定しないでメソッドを呼び出した場合、デフォルトでは「カスタムリンク」に設定されます。

* `o`  — カスタムリンク
* `d`  — ダウンロードリンク
* `e`  — 離脱リンク

> [!TIP] この変数はメソッドの2番目のパラメー `tl()` ターで、通常、スタンドアロン変数として設定する必要はありません。 ただし、メソッドの引数 `linkType` として値を設定しない場合は、変数を使用でき `tl()` ます。

```js
s.linkType = "e";
```

## 例   

次の2つのリンクトラッキングコールの例は、機能的に同じです。 同じリンクトラッキングヒットを達成する方法は異なります。

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
