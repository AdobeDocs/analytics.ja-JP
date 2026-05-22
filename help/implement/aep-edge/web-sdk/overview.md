---
title: Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装
description: Web SDKを使用して、Adobe Analyticsにデータを送信します。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/8p05Bfxo37frjI9pPQOPHPtzt8yxPmFXj-nYW00IYfE'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 42%

---

# Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) を使用して、データを Adobe Analytics に送信できます。 Web SDKを実装するには、主に2つの方法があり、各メソッドには2つの実装タイプがあります。

| | **AppMeasurementからの移行** | **クリーン Web SDKの実装** |
| --- | --- | --- |
| **タグを使用** | [Analytics拡張機能からWeb SDK拡張機能への移行](analytics-extension-to-web-sdk.md) | [Web SDK拡張機能を使用してAdobe Analyticsにデータを送信](web-sdk-tag-extension.md) |
| **JavaScriptを使用** | [AppMeasurementからWeb SDK JavaScript ライブラリへの移行](appmeasurement-to-web-sdk.md) | [Web SDK JavaScript ライブラリを使用してAdobe Analyticsにデータを送信する](web-sdk-javascript-library.md) |

組織で新しいWeb SDKの実装が必要で、将来的にCustomer Journey Analyticsを使用する予定がある場合は、Adobeで独自のスキーマを使用してクリーンなWeb SDKの実装をお勧めします。 Customer Journey Analytics ユーザーガイドの「[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)を介したデータの取り込み」を参照してください。

## その他のリソース

タグは高度にカスタマイズできます。 実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)：インターフェイスの仕組みと使用可能な拡張機能について説明します。

- [Adobe Experience Platform Web SDKのドキュメント](https://experienceleague.adobe.com/docs/web-sdk.html?lang=ja)
