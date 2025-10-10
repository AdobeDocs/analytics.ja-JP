---
title: サーバー
description: 「サーバー」ディメンションを設定します。
feature: Appmeasurement Implementation
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 74%

---

# サーバー

`server` 変数は通常、サイトのホスト名を保存します。これは、複数のドメインのデータを含むレポートスイートで一般的に使用されます。機能的には prop と同じです。

## Web SDKを使用したサーバー

サーバーは次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.server`
* [&#x200B; データ オブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.server`

## Adobe Analytics拡張機能を使用したサーバー

サーバーは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストをAdobe Analyticsに設定し、「[!UICONTROL &#x200B; アクションタイプ &#x200B;]」を [!UICONTROL &#x200B; 変数を設定 &#x200B;] に設定します。
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
