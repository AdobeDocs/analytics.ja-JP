---
title: SSL 証明書のライセンス
description: 顧客管理証明書の手続き
feature: Regional Data Collection
exl-id: 7d1373c8-6f7b-4ce7-a555-d3d506e08d17
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 100%

---

# SSL／TLS 証明書のライセンス

アドビでは、[Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=ja) を利用して、追加費用なしで証明書を管理することをお勧めします。Adobe Managed Certificate Program は完全自動化されており、証明書の期限切れによる影響を回避するために、適時に証明書を更新できるようにします。

[Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=ja) を使用しない場合、ファーストパーティ cookie に使用する SSL／TLS 証明書を提供する必要があります。

お客様が独自の証明書を用意する場合は、購入やメンテナンスを独自に継続していただく必要があります。SSL／TLS 証明書には、無制限のサーバーライセンスが含まれている必要があります。

証明書のセキュリティを確保するには、アドビから証明書署名要求 [CSR] を取得し、適切な認証局に証明書の署名を依頼します。実装用の署名済み証明書をアドビに提出します。この手順に従うことで、証明書の鍵のセキュリティが維持されます。アドビカスタマーケアが、証明書のセキュリティ確保をお手伝いします。

証明書のメンテナンスの一環として、証明書の有効期限が切れる 1 ヶ月以上前に、適切な認証局に依頼して更新された証明書を取得し、アドビに提出します。この証明書は、以前に使用したものと同じ CSR を使用する必要があります。CSR のコピーが必要な場合や、新しい鍵を使用して CSR を生成したい場合は、アドビにお問い合わせください。

カスタマーケアへのお問い合わせは、customercare@adobe.com または 1-800-497-0335 までお願いいたします。

一般的に使用されている認証局には、DigiCert、Comodo、GeoTrust などがあります。
