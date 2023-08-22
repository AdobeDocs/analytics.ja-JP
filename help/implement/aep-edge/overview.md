---
title: Adobe Experience Platform Edge を使用した Adobe Analytics の実装
description: Adobe Analytics における Experience Platform の XDM データの使用の概要
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
source-git-commit: e0f08e6e53b6d7001bd1163a65facda8e21c91fd
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 39%

---

# Adobe Experience Platform Edge を使用した Adobe Analytics の実装

Adobe Experience Platform Edge を使用すると、複数の製品用のデータを一元的な場所に送信できます。Experience Edge は、適切な情報を目的の製品に転送します。この概念を使用すると、特に複数のデータソリューションにまたがる実装作業を統合できます。

アドビでは、Experience Edge にデータを送信する 3 つの主な方法を提供しています。

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：Adobe Experience Platform のデータ収集で、Web SDK 拡張機能を使用して Edge にデータを送信します。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：Adobe Experience Platform のデータ収集で、Mobile SDK 拡張機能を使用して Edge にデータを送信します。
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**:API を使用して Edge に直接データを送信します。



## Adobe Analyticsによる Experience Edge データの処理方法

Experience Edge に送信されるデータは、 [XDM（エクスペリエンスデータモデル）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja). XDM を使用すると、イベントの一部として定義されるフィールドを柔軟に設定できます。 イベントがAdobe Analyticsに到達すると、これらのイベントは、Adobe Analyticsで処理できる、より構造化されたデータ（ページビューやリンクイベント）に変換されます。

XDM 自体は、ページビューやリンクイベントの定義方法を規定しているわけではなく、Adobe Analyticsに対してペイロードの処理方法を指示するわけでもありません。 例えば、ページビューやリンクイベントに関連して表示される、標準搭載の XDM フィールド ( 例： `eventType`, `web.webPageDetails.pageViews`または `web.webInteraction.linkEvents` は、完全に実装に依存せず、Adobe Analyticsには関連しません。

ページビューとリンクイベントを適切に処理するには、次のロジックがAdobeExperience Edge ネットワークに送信され、Adobe Analyticsに転送されるデータに適用されます。

| XDM ペイロードに含まれる内容： | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` または `web.webPageDetails.URL` およびいいえ `web.webInteraction.type` | ペイロードを考慮する **ページビュー** |
| `web.webInteraction.type` および (`web.webInteraction.name` または `web.webInteraction.url`) | ペイロードを考慮する **リンクイベント** |
| `web.webInteraction.type` および (`web.webPageDetails.name` または `web.webPageDetails.url`) | ペイロードを考慮する **リンクイベント** <br/>`web.webPageDetails.name` および `web.webPageDetails.URL` が `null` |
| いいえ `web.webInteraction.type` および ( いいえ `webPageDetails.name` およびいいえ `web.webPageDetails.URL`) | ペイロードを破棄し、データを無視する |

{style="table-layout:auto"}

