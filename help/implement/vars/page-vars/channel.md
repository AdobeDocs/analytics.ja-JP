---
title: チャネル
description: 「サイトセクション」ディメンションを設定します。
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 75%

---

# チャネル

`channel` 変数は、通常、特定のページが存在するサイトのセクションを格納します。サイトで最も人気のあるグループを判断すると役立ちます。この変数は、「サイトセクション」ディメンションを入力します。

## Web SDKを使用したチャネル

チャネルは、次の変数にマッピングされます。

* [XDM オブジェクト ](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [Data オブジェクト ](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel` または `data.__adobe.analytics.ch`

## Adobe Analytics拡張機能を使用したチャネル

チャネルは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL  拡張機能 ]」ドロップダウンリストをAdobe Analyticsに設定し、「[!UICONTROL  アクションタイプ ]」を [!UICONTROL  変数を設定 ] に設定します。
6. [!UICONTROL チャネル]セクションを見つけます。

channel は任意の文字列値またはデータ要素に設定できます。

## AppMeasurementの s.channel と Analytics 拡張機能のカスタムコードエディター

`s.channel` 変数は、通常、ページのサイトセクションを含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。

```js
s.channel = "Example site section";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.channel = digitalData.page.category.primaryCategory;
```
