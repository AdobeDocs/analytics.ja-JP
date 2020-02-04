---
title: linkType
description: linkType変数を使用して、ヒットが属するリンクトラッキングディメンションを特定します。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkType

リンクトラッキングのヒットには、次の3つのディメンションのいずれかを設定できます。

* カスタムリンク
* 離脱リンク
* ダウンロードリンク

この変数を使 `linkType` 用して、次の関数の実行時に入力するディメンションを決定 `tl()` します。

## Adobe Experience Platform Launchのリンクタイプ

ビーコンを送信するルールを設定する場合は、リンクタイプを設定します。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で「+」アイコンをクリックします
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクションタイプ [!UICONTROL 」を「送信ビーコン] 」に設定します。
6. ラジオボタンをク `s.tl()` リックすると、「リンクタイプ」ドロ [!UICONTROL ップダウンが表示され] ます。

このドロップダウンを「カスタムリンク [!UICONTROL 」、「ダウンロ]ードリンク [!UICONTROL 」または「離脱リ]ンク」に設定できます 。

## AppMeasurementのs.linkTypeとカスタムコードエディターの起動

変数 `s.linkType` は、次の3つの1文字の値のいずれかを受け取る文字列です。 `o`、 `d`または `e`。 リンクタイプ `tl()` を指定せずに関数を呼び出した場合、デフォルトでは「カスタムリンク」に設定されます。

* `o`  — カスタムリンク
* `d`  — ダウンロードリンク
* `e`  — 離脱リンク

> [!TIP] この変数は関数の2番目のパラメー `tl()` ターで、通常、スタンドアロン変数として設定する必要はありません。 ただし、関数の引数と `linkType` して値を設定しない場合は、この変数を使用でき `tl()` ます。

```js
s.linkType = "e";
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
