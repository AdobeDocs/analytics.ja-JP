---
title: linkName
description: カスタムリンクヒットの名前を設定します。
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkName

この変数を使 `linkName` 用して、次の関数を実行する際のカスタムリンク、ダウンロードリンクまたは離脱リンクのディメンション値を決定 `tl()` します。

この変数が空白の場合、AppMeasurementは変数に戻り `linkURL` ます。

## Adobe Experience Platform Launchのリンク名

ビーコンを送信するルールを設定する際に、リンク名フィールドを設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で「+」アイコンをクリックします
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクションタイプ [!UICONTROL 」を「送信ビーコン] 」に設定します。
6. ラジオボタンをク `s.tl()` リックすると、「リンク名」フィ [!UICONTROL ールドが表示され] ます。

## AppMeasurementのs.linkNameとカスタムコードエディターの起動

変数 `s.linkName` は、カスタムリンク、ダウンロードリンクまたは離脱リンク（内容に応じて）のディメンション値を決定する `s.linkType` 文字列です。 最大100バイトまで保持できます。

> [!TIP] この変数は関数の3番目のパラメー `tl()` ターで、通常、スタンドアロン変数として設定する必要はありません。 ただし、関数の引数と `linkName` して値を設定しない場合は、この変数を使用でき `tl()` ます。

```js
s.linkName = "Example custom link";
```

## 例

次の2つのリンクトラッキングコールの例は、機能的に同じです。 同じリンクトラッキングヒットを達成するには、異なる方法があります。

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
