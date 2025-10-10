---
title: Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装
description: Web SDKを使用してAdobe Analyticsにデータを送信します。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 40%

---

# Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) を使用して、データを Adobe Analytics に送信できます。Web SDKを実装する主な方法は 2 つあり、それぞれの方法には次の 2 つの実装タイプがあります。

| | **AppMeasurementからの移行** | **Web SDKのクリーンな実装** |
| --- | --- | --- |
| **タグを使用** | [Analytics 拡張機能から Web SDK拡張機能への移行 ](analytics-extension-to-web-sdk.md) | [Web SDK拡張機能を使用したAdobe Analyticsへのデータの送信 ](web-sdk-tag-extension.md) |
| **JavaScriptの使用** | [AppMeasurementから Web SDK JavaScript ライブラリへの移行 ](appmeasurement-to-web-sdk.md) | [Web SDK JavaScript ライブラリを使用したAdobe Analyticsへのデータの送信 ](web-sdk-javascript-library.md) |

組織で新しい web SDKの実装が必要であり、今後Customer Journey Analyticsを使用する予定がある場合、Adobeは独自のスキーマを使用して、クリーンな web SDKの実装をお勧めします。 Customer Journey Analytics ユーザーガイドの [Adobe Experience Platform Web SDKを使用したデータの取り込み ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) を参照してください。

## その他のリソース

タグは高度にカスタマイズできます。実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)：インターフェイスの仕組みと使用可能な拡張機能について説明します。

- [Adobe Experience Platform Web SDK ドキュメント](https://experienceleague.adobe.com/docs/web-sdk.html?lang=ja)
