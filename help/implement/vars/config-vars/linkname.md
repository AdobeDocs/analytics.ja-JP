---
title: linkName
description: カスタムリンクヒットの名前を設定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkName

この変数を使 `linkName` 用して、次のメソッドを実行する際に、カスタムリンク、ダウンロードリンクまたは離脱リンクのディメンション値を決定 [`tl()`](../functions/tl-method.md) します。

この変数が空白の場合、AppMeasurementは変数に戻り [`linkURL`](linkurl.md) ます。

## Adobe Experience Platform Launchのリンク名

ビーコンを送信するルールを設定する際に、リンク名フィールドを設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. 下の「 [!UICONTROL Actions]+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、「ビーコンの送 [!UICONTROL Action Type] 信」に設定します。
6. ラジオボタンをク `s.tl()` リックすると、フィールドが表示 [!UICONTROL Link Name] されます。

## AppMeasurementのs.linkNameとカスタムコードエディターの起動

変数は `s.linkName` 、カスタムリンク、ダウンロードリンクまたは離脱リンクのディメンション値を決定する文字列(内容に応じ [`s.linkType`](linktype.md) て異なります)。 最大100バイトまで保持できます。

> [!TIP] この変数はメソッドの3番目のパラメー `tl()` ターで、通常、スタンドアロン変数として設定する必要はありません。 ただし、メソッドの引数 `linkName` として値を設定しない場合は、変数を使用でき `tl()` ます。

```js
s.linkName = "Example custom link";
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
