---
title: チャネル
description: 「サイトセクション」ディメンションを設定します。
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 74%

---

# チャネル

`channel` 変数は、通常、特定のページが存在するサイトのセクションを格納します。サイトで最も人気のあるグループを判断すると役立ちます。この変数は、「サイトセクション」ディメンションを入力します。

## Web SDK を使用したチャネル

チャネルは [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) XDM フィールドの下 `web.webPageDetails.siteSection`.

## Adobe Analytics拡張機能を使用するチャネル

チャネルは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. [!UICONTROL チャネル]セクションを見つけます。

channel は任意の文字列値またはデータ要素に設定できます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.channel

`s.channel` 変数は、通常、ページのサイトセクションを含む文字列です。最大値は 100 バイトです。より長い値は切り捨てられます。

```js
s.channel = "Example site section";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.channel = digitalData.page.category.primaryCategory;
```
