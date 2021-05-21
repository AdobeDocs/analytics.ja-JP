---
title: 設定変数
description: 設定変数を使用して、データの収集方法を決定します。
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '123'
ht-degree: 100%

---

# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。通常、ディメンションや指標の値は含まれません。

## 設定変数の設定

`AppMeasurement.js` を使用した JavaScript 実装では、通常、設定変数は JS ファイルの先頭に設定されます。

Adobe Experience Platform Launch を使用した実装では、通常、設定変数は Adobe Analytics 拡張機能を設定することで見つかります。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 編集するプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブをクリックしてから、Adobe Analytics で「[!UICONTROL 設定]」をクリックします。

>[!IMPORTANT]
>
>トラッキングメソッド（[`t()`](../functions/t-method.md) または [`tl()`](../functions/tl-method.md)）を呼び出す前に、すべての設定変数が設定されていることを確認します。[`doPlugins()`](../functions/doplugins.md) 関数内で設定変数を設定しないでください。
