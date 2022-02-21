---
title: サーバー
description: 「サーバー」ディメンションを設定します。
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 100%

---

# サーバー

`server` 変数は通常、サイトのホスト名を保存します。これは、複数のドメインのデータを含むレポートスイートで一般的に使用されます。機能的には prop と同じです。

## Adobe Experience Platform のタグを使用したサーバー

サーバーは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL サーバー]セクションを探します。

サーバーは任意の文字列値またはデータ要素に設定できます。

## AppMeasurement および カスタムコードエディターの s.server

`s.server` 変数は、通常、サイトのホスト名を含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
