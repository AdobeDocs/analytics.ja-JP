---
title: linkType
description: linkType 変数は、ヒットが属するリンクトラッキングディメンションを特定するのに使用します。
translation-type: ht
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
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「ビーコンを送信」に設定します。
6. `s.tl()` ラジオボタンをクリックすると、「[!UICONTROL リンクタイプ]」ドロップダウンが表示されます。

このドロップダウンを「[!UICONTROL カスタムリンク]」、「[!UICONTROL ダウンロードリンク]」または「[!UICONTROL 出口リンク]」に設定できます。

## AppMeasurement および Launch カスタムコードエディターの s.linkType

`s.linkType` 変数は、`o`、`d`、`e` の 3 つの 1 文字の値のいずれかを受け取る文字列です。リンクタイプを指定せずに `tl()` メソッドを呼び出した場合、デフォルトでは「カスタムリンク」に設定されます。

* `o` - カスタムリンク
* `d` - ダウンロードリンク
* `e` - 出口リンク

>[!TIP] この変数は `tl()` メソッドの 2 番目のパラメーターで、通常、スタンドアロン変数として設定する必要はありません。ただし、`linkType` メソッドの引数として値を設定しない場合は、`tl()` 変数を使用できます。

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
