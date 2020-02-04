---
title: 設定変数
description: 設定変数を使用して、データの収集方法を決定します。
translation-type: tm+mt
source-git-commit: e9a876a1f562333056387d63de46a9cfe3fb3939

---


# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。通常、ディメンションや指標の値は含まれません。

## 設定変数の設定

を使用したJavaScript実装で `AppMeasurement.js`は、通常、設定変数はJSファイルの先頭に設定されます。

Adobe Experience Platform Launchを使用した実装では、通常、設定変数はAdobe Analytics拡張を設定することで見つかります。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 編集するプロパティをクリックします。
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] track関数（または）を呼び出す前に、すべての設定変数が設定されていることを`t()` 確認し `tl()`ます。 関数内で設定変数を設定しないでく `doPlugins()` ださい。
