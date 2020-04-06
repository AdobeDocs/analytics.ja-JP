---
title: linkName
description: カスタムリンクヒットの名前を設定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkName

Use the `linkName` variable to determine the dimension value of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

この変数が空白の場合、AppMeasurement は [`linkURL`](linkurl.md) 変数に戻ります。

## Adobe Experience Platform Launch の「リンク名」

ビーコンを送信するルールを設定する際に、リンク名フィールドを設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Name] field.

## AppMeasurement および Launch カスタムコードエディターの s.linkName

`s.linkName` 変数は、カスタムリンク、ダウンロードリンクまたは出口リンク（[`s.linkType`](linktype.md) に応じて）のディメンション値を決定する文字列です。最大 100 バイトまで保持できます。

>[!TIP] この変数はメソッドの3番目のパラメー `tl()` ターで、通常、スタンドアロン変数として設定する必要はありません。 However, you can use the `linkName` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkName = "Example custom link";
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
