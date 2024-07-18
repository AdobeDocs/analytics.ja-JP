---
title: Adobe Experience Platform Edge を使用した Adobe Analytics の実装
description: Adobe Analytics における Experience Platform の XDM データの使用の概要
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 100%

---

# Adobe Experience Platform Edge Network を使用した Adobe Analytics の実装

Adobe Experience Platform Edge Network を使用すると、複数の製品宛てのデータを一元的な場所に送信できます。Edge Network は、適切な情報を目的の製品に転送します。この概念を使用すると、特に複数のデータソリューションにまたがる実装作業を統合できます。

アドビでは、Edge Network にデータを送信する 3 つの主な方法を提供しています。

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：Adobe Experience Platform のデータ収集で、Web SDK 拡張機能を使用して Edge にデータを送信します。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：Adobe Experience Platform のデータ収集で、Mobile SDK 拡張機能を使用して Edge にデータを送信します。
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**：API を使用して Edge に直接データを送信します。



## Adobe Analytics が Edge Network データを処理する方法

Adobe Experience Platform Edge Network に送信されるデータは、次の 2 つの形式に従うことができます。

* XDM オブジェクト：[XDM（エクスペリエンスデータモデル）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)に基づくスキーマに準拠します。XDM では、どのフィールドをイベントの一部として定義するかを柔軟に指定できます。イベントが Adobe Analytics に到達すると、イベントは Adobe Analytics が処理できる形式に変換されます。
* データオブジェクト： Adobe Analytics にマッピングされた特定のフィールドを使用して、Edge Network にデータを送信します。Edge Network は、これらのフィールドの存在を検出し、スキーマに準拠する必要なく、Adobe Analytics に転送します。


Edge Network は、次のロジックを使用して Adobe Analytics のページビューとリンクイベントを決定します。

| XDM ペイロードには次のものが含まれます。 | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` or `web.webPageDetails.URL` and no `web.webInteraction.type` | ペイロードを&#x200B;**ページビュー**&#x200B;とみなします |
| `web.webInteraction.type` and (`web.webInteraction.name` or `web.webInteraction.url`) | ペイロードを&#x200B;**リンクイベント**&#x200B;とみなします |
| `web.webInteraction.type` and (`web.webPageDetails.name` or `web.webPageDetails.url`) | ペイロードを&#x200B;**リンクイベント**&#x200B;とみなし、<br/>`web.webPageDetails.name` と `web.webPageDetails.URL` は `null` に設定されます |
| no `web.webInteraction.type` and (no `webPageDetails.name` and no `web.webPageDetails.URL`) | ペイロードをドロップし、データを無視します |

{style="table-layout:auto"}

詳しくは、[Adobe Analytics ExperienceEvent フル拡張スキーマフィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=ja)を参照してください。
