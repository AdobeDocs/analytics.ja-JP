---
title: trackingServer
description: HTTP 経由でAdobeにデータを送信するために使用されるドメイン。
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 13%

---

# trackingServer

>[!IMPORTANT]
>
>この変数は非推奨（廃止予定）です。 HTTPS が普及しているので、代わりに [`trackingServerSecure`](trackingserversecure.md) を使用してください。

`trackingServer` 変数は、HTTP 経由でAppMeasurementからAdobeにデータを送信する際に使用するドメインを決定します。 この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

[Adobe Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home) より前は、この変数もサードパーティ Cookie が設定された場所を特定していました。 Adobeでは、可能な限り、すべての実装で ID サービスを使用することを強くお勧めします。

`trackingServer` が設定されていない場合、AppMeasurementは [`trackingServerSecure`](trackingserversecure.md) をフォールバックとして使用します。 古い実装の多くは `trackingServerSecure` を設定せず、`trackingServer` をセキュリティで保護されたページへのフォールバックとして使用しています。 HTTPS の普及に伴い、Adobeでは可能な限り `trackingServerSecure` を使用することをお勧めします。
