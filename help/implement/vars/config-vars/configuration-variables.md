---
title: 設定変数
description: 設定変数を使用して、データの収集方法を決定します。
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 65%

---

# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。通常、ディメンションや指標の値は含まれません。

## 設定変数の設定

Web SDK 拡張機能または Analytics 拡張機能を使用した実装では、通常、設定変数は拡張機能の設定にあります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」タブをクリックしてから、拡張機能の下の「[!UICONTROL &#x200B; 設定 &#x200B;]」をクリックします。

`AppMeasurement.js` を使用した JavaScript 実装では、通常、設定変数は JS ファイルの先頭に設定されます。

>[!IMPORTANT]
>
>トラッキングメソッド（[`t()`](../functions/t-method.md) または [`tl()`](../functions/tl-method.md)）を呼び出す前に、すべての設定変数が設定されていることを確認します。 [`doPlugins()`](../functions/doplugins.md) 関数内で設定変数を設定しないでください。
