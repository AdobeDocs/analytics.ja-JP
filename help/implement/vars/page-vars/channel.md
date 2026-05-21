---
title: チャネル
description: 「サイトセクション」ディメンションを設定します。
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
TQID: https://experienceleague.adobe.com/hctVvVL98TCC2y6dUvO-5jhO40CkYwRB8ygBUcWu684
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 83%

---

# チャネル

`channel` 変数は、通常、特定のページが存在するサイトのセクションを格納します。 サイトで最も人気のあるグループを判断すると役立ちます。 この変数は、「サイトセクション」ディメンションを入力します。

## Web SDKを使用したチャネル

チャネルは次の変数にマッピングされます。

* [XDM オブジェクト &#x200B;](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [&#x200B; データオブジェクト &#x200B;](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel`または`data.__adobe.analytics.ch`

## Adobe Analytics拡張機能を使用したチャネル

チャネルは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. [!UICONTROL チャネル]セクションを見つけます。

channel は任意の文字列値またはデータ要素に設定できます。

## AppMeasurementのs.channelとAnalytics拡張機能のカスタムコードエディター

`s.channel` 変数は、通常、ページのサイトセクションを含む文字列です。 最大値は 100 バイトです。より長い値は切り捨てられます。

```js
s.channel = "Example site section";
```

`digitalData` [データレイヤー](../../prepare/data-layer.md)を使用する場合：

```js
s.channel = digitalData.page.category.primaryCategory;
```
