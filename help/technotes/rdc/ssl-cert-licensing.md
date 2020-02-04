---
title: SSL 証明書のライセンス
description: 顧客管理証明書の証明書手続き
translation-type: tm+mt
source-git-commit: 290838566b86f71902abd303b5c43dd2661d3ce1

---


# SSL/TLS証明書のライセンス

アドビでは、 [Adobe Managed Certificate Programを使用して、追加費用なしで証明書を管理することをお勧めします](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html)。  Adobe Managed Certificateプログラムは完全に自動化され、証明書が期限切れになったために影響を及ぼさないように、適時に更新されるようにします。

Adobe Managed Certificate Programを使用しないように選択した場合 [](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) 、ファーストパーティcookieに使用するSSL/TLS証明書を提供する必要があります。

お客様が独自の証明書を用意する場合は、購入やメンテナンスを独自に継続していただく必要があります。SSL/TLS証明書に無制限のサーバーライセンスが含まれている必要があります。

証明書セキュリティを確保するには、アドビから証明書署名要求 [CSR] を取得し、必要な認証局に証明書の署名を依頼します。  実装用の署名済み証明書をアドビに提供します。  このプロセスに従うと、証明書のキーのセキュリティが維持されます。  アドビカスタマーケアがこのプロセスを支援します。

証明書のメンテナンスの一環として、証明書の有効期限が切れる1か月以上前に、必要な認証局と手配し、更新された証明書を取得してアドビに提供します。  この証明書は、以前に使用したのと同じCSRを使用する必要があります。  CSRのコピーが必要な場合や、新しいキーを使用して新しいCSRを生成したい場合は、アドビにお問い合わせください。

カスタマーケアにお問い合わせは、customercare@adobe.comまたは1-800-497-0335にお問い合わせください。

一般的に使用される認証機関には、DigiCert、Comodo、GeoTrustがあります。
