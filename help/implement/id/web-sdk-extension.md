---
title: Web SDK タグ拡張機能を使用した訪問者の識別
description: Web SDK タグ拡張機能を実装する際に、訪問者を正しく識別します。
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Web SDK タグ拡張機能を使用した訪問者の識別

Adobe Experience Platform Data Collection の Web SDK タグ拡張機能を使用すると、タグ管理インターフェイスを使用して web SDKを実装できます。 クロスドメイン ID 共有や訪問者プロファイル移行などの高度なシナリオは、拡張機能のルールとアクションを通じて簡単に設定できます。 Web SDKの今後の展開を活用して、Customer Journey Analyticsへのシームレスなアップグレードをサポートします。

ID データを拡張して、XDM の `identityMap` を使用してカスタム ID と複数の名前空間をサポートすることができます。 Adobeでは、高度なシナリオを実現するために、他の ID 管理オプションを使用して、Adobe Experience Cloud ID サービスを Analytics のプライマリ ID として使用することをお勧めします。

訪問者 ID サービスはタグ拡張機能にネイティブにベイクされるので、**[!UICONTROL Edge Domain]** を目的の値に設定する必要があります。 このフィールドが正しく設定されると、追加の設定なしに訪問者の識別が機能します。

>[!NOTE]
>
>Web SDK タグ拡張機能を使用している場合は、訪問者 ID サービスタグ拡張機能を含めないでください。 訪問者 ID サービスタグ拡張機能は、[Adobe Analytics extension](analytics-extension.md) を使用する場合にのみ必要です。
