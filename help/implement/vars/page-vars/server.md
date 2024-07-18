---
title: サーバー
description: 「サーバー」ディメンションを設定します。
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 74%

---

# サーバー

`server` 変数は通常、サイトのホスト名を保存します。これは、複数のドメインのデータを含むレポートスイートで一般的に使用されます。機能的には prop と同じです。

## Web SDK を使用したサーバー

サーバーは次の変数にマッピングされます。

* [XDM オブジェクト ](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.server`
* [ データ オブジェクト ](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.server`

## Adobe Analytics拡張機能を使用したサーバー

サーバーは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL  拡張機能 ]」ドロップダウンリストをAdobe Analyticsに設定し、「[!UICONTROL  アクションタイプ ]」を [!UICONTROL  変数を設定 ] に設定します。
6. [!UICONTROL サーバー]セクションを探します。

サーバーは任意の文字列値またはデータ要素に設定できます。

## AppMeasurementの s.server と Analytics 拡張機能のカスタムコードエディター

`s.server` 変数は、通常、サイトのホスト名を含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
