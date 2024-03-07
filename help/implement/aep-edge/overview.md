---
title: Adobe Experience Platform Edge を使用した Adobe Analytics の実装
description: Adobe Analytics における Experience Platform の XDM データの使用の概要
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 23%

---

# Adobe Experience Platform Edge Network を使用したAdobe Analyticsの実装

Adobe Experience Platform Edge Network を使用すると、複数の製品用のデータを一元的な場所に送信できます。 Edge ネットワークは、適切な情報を目的の製品に転送します。 この概念を使用すると、特に複数のデータソリューションにまたがる実装作業を統合できます。

Adobeは、Edge ネットワークにデータを送信する 3 つの主な方法を提供します。

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：Adobe Experience Platform のデータ収集で、Web SDK 拡張機能を使用して Edge にデータを送信します。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：Adobe Experience Platform のデータ収集で、Mobile SDK 拡張機能を使用して Edge にデータを送信します。
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**:API を使用して Edge に直接データを送信します。



## Adobe Analyticsによる Edge Network データの処理方法

Adobe Experience Platform Edge Network に送信されるデータは、次の 2 つの形式に従うことができます。

* XDM オブジェクト： [XDM（エクスペリエンスデータモデル）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja). XDM を使用すると、イベントの一部として定義されるフィールドを柔軟に設定できます。 イベントがAdobe Analyticsに到達すると、イベントはAdobe Analyticsで処理できる形式に変換されます。
* データオブジェクト： Adobe Analyticsにマッピングされた特定のフィールドを使用して、Edge Network にデータを送信します。 Edge ネットワークは、これらのフィールドの存在を検出し、スキーマに準拠する必要なく、Adobe Analyticsに転送します。


Edge Network は、次のロジックを使用してAdobe Analyticsのページビューとリンクイベントを決定します

| XDM ペイロードに含まれる内容： | ADOBE ANALYTICS... |
|---|---|
| `web.webPageDetails.name` または `web.webPageDetails.URL` およびいいえ `web.webInteraction.type` | ペイロードを考慮する **ページビュー** |
| `web.webInteraction.type` および (`web.webInteraction.name` または `web.webInteraction.url`) | ペイロードを考慮する **リンクイベント** |
| `web.webInteraction.type` および (`web.webPageDetails.name` または `web.webPageDetails.url`) | ペイロードを考慮する **リンクイベント** <br/>`web.webPageDetails.name` および `web.webPageDetails.URL` が `null` |
| いいえ `web.webInteraction.type` および ( いいえ `webPageDetails.name` およびいいえ `web.webPageDetails.URL`) | ペイロードを破棄し、データを無視する |

{style="table-layout:auto"}

詳しくは、 [Adobe Analytics ExperienceEvent Full Extension スキーマフィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html) を参照してください。
