---
title: 設定変数
description: 設定変数を使用して、データの収集方法を決定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。通常、ディメンションや指標の値は含まれません。

## 設定変数の設定

`AppMeasurement.js` を使用した JavaScript 実装では、通常、設定変数は JS ファイルの先頭に設定されます。

Adobe Experience Platform Launch を使用した実装では、通常、設定変数は Adobe Analytics 拡張機能を設定することで見つかります。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 編集するプロパティをクリックします。
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

>[!IMPORTANT] トラッキングメソッド（または）を呼び出す前に、すべての設定変数が設定されている[`t()`](../functions/t-method.md) ことを確認 [`tl()`](../functions/tl-method.md)します。 [`doPlugins()`](../functions/doplugins.md) 関数内で設定変数を設定しないでください。
