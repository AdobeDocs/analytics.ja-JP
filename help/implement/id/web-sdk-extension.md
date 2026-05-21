---
title: Web SDK タグ拡張機能を使用した訪問者特定
description: Web SDK タグ拡張機能を実装する際に、訪問者を正しく識別する。
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: https://experienceleague.adobe.com/W42VkHT5yCW0yO-FbiAFHHKM8dF5NgCveZYGFOs7sYk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
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
