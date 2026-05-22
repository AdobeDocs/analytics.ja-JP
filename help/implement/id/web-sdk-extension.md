---
title: Web SDK タグ拡張機能を使用した訪問者特定
description: Web SDK タグ拡張機能を実装する際に、訪問者を正しく識別する。
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: 'https://experienceleague.adobe.com/4PVDioBDa-1VXg9Fpy0wA8-RZZYSXzVijj-b2kdEALQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 0%

---

# Web SDK タグ拡張機能を使用した訪問者特定

Adobe Experience Platform Data CollectionのWeb SDK タグ拡張機能を使用すると、タグ管理インターフェイスを使用してWeb SDKを実装できます。 クロスドメイン IDの共有や訪問者プロファイルの移行などの高度なシナリオは、拡張ルールやアクションを通じて簡単に設定できます。 Web SDKを利用すれば、実装の将来性を確保し、Customer Journey Analyticsへのシームレスなアップグレードを実現できます。

ID データを拡張して、XDMの`identityMap`を使用してカスタム IDと複数の名前空間をサポートできます。 Adobeでは、Analyticsの主要なIDとしてAdobe Experience Cloud ID サービスを使用し、高度なシナリオには他のID管理オプションを使用することをお勧めします。

訪問者ID サービスはタグ拡張機能にネイティブに組み込まれているため、**[!UICONTROL Edge ドメイン]**&#x200B;を目的の値に設定する必要があるだけです。 このフィールドが正しく設定されている場合、訪問者の識別は追加の設定なしで機能します。

>[!NOTE]
>
>Web SDK タグ拡張機能を使用する場合は、訪問者ID サービスタグ拡張機能を含めないでください。 訪問者ID サービスタグ拡張機能は、[Adobe Analytics拡張機能](analytics-extension.md)を使用する場合にのみ必要です。
