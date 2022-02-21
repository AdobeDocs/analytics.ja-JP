---
title: 設定変数
description: 設定変数を使用して、データの収集方法を決定します。
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%

---

# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。通常、ディメンションや指標の値は含まれません。

## 設定変数の設定

`AppMeasurement.js` を使用した JavaScript 実装では、通常、設定変数は JS ファイルの先頭に設定されます。

Adobe Experience Platform のタグを使用した実装では、通常、設定変数は Adobe Analytics 拡張機能を設定することで見つかります。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
1. 編集するプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブをクリックしてから、Adobe Analytics で「[!UICONTROL 設定]」をクリックします。

>[!IMPORTANT]
>
>トラッキングメソッド（[`t()`](../functions/t-method.md) または [`tl()`](../functions/tl-method.md)）を呼び出す前に、すべての設定変数が設定されていることを確認します。[`doPlugins()`](../functions/doplugins.md) 関数内で設定変数を設定しないでください。
