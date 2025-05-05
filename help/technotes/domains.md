---
title: Adobe Analyticsが使用するドメイン
description: Adobe Analyticsを使用して最適なエクスペリエンスを得るには、組織のファイアウォールを通過してこれらのドメインを許可します。
feature: Data Configuration and Collection
exl-id: 41f11b71-c97e-45e8-9ca5-7992f02579f5
source-git-commit: c1d1693bef617e3ebd6bf4f007c2235b2098a016
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 13%

---

# Adobe Analyticsが使用するドメイン

一部のファイアウォール設定は、Adobe Analyticsが製品インターフェイスに使用するドメインをブロックします。 このドメインのリストを使用して組織のネットワーク設定を変更し、組織内からの製品アクセスを許可できます。 Adobeは、最適なエクスペリエンスを得るために、組織のファイアウォールを通じてこれらのドメインを許可することをお勧めします。

| 技術 | ドメイン |
| --- | --- |
| Adobe Analytics ドメイン | `adobe.com`、`adobe.net`、`adobe.io` |
| Adobe Analytics レガシードメイン | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud ドメイン

上記のドメインに加えて、Adobe Experience Cloudでは、データ収集とレポートの書き出しに複数のドメインを使用します。 このドメインのリストについては、[Adobe Experience Cloudで使用されるドメイン ](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/domains) を参照してください。

>[!MORELIKETHIS]
>
>[Adobe Analyticsで使用される IP アドレス ](ip-addresses.md)
>
>[Adobe Experience Cloudが使用するドメイン ](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/domains)
