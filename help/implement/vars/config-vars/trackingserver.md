---
title: trackingServer
description: HTTP経由でAdobeにデータを送信するために使用されるドメイン。
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
TQID: https://experienceleague.adobe.com/6H8uZ4J-mT8NcC4OiiTgtBnP8eAgaMMzxzUHkS-9kGs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 120
ht-degree: 19%

---

# trackingServer

>[!IMPORTANT]
>
>この変数は非推奨です。 HTTPSが普及している場合は、代わりに[`trackingServerSecure`](trackingserversecure.md)を使用してください。

`trackingServer`変数は、AppMeasurementがHTTP経由でAdobeにデータを送信するために使用するドメインを決定します。 この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/ja/docs/id-service/using/home)以前は、この変数はサードパーティ Cookieの設定場所も決定していました。 Adobeでは、可能な限り、すべての実装でID サービスを使用することを強くお勧めします。

[`trackingServerSecure`](trackingserversecure.md)が設定されていない場合、AppMeasurementは`trackingServer`をフォールバックとして使用します。 古い実装の多くは`trackingServerSecure`を設定せず、`trackingServer`を安全なページのフォールバックとして使用しています。 HTTPSの普及に伴い、Adobeでは、可能な限り`trackingServerSecure`を使用することをお勧めします。
