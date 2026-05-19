---
title: Adobe Analyticsで使用されるドメイン
description: Adobe Analyticsを利用して、最適なエクスペリエンスを実現するために、組織のファイアウォールを通じてこれらのドメインを許可します。
feature: Data Configuration and Collection
exl-id: 41f11b71-c97e-45e8-9ca5-7992f02579f5
TQID: https://experienceleague.adobe.com/y5UXvG8gVAw4fp-Hep-nNHixMQydt-xjr5MGNbp0SQk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 9%

---

# Adobe Analyticsで使用されるドメイン

一部のファイアウォール設定では、Adobe Analyticsが製品インターフェイスに依存するドメインをブロックします。 このドメインのリストを使用して、組織のネットワーク設定を変更し、組織内から製品にアクセスできるようにすることができます。 Adobeでは、最適なエクスペリエンスを実現するために、組織のファイアウォールを通じてこれらのドメインを許可することをお勧めします。

| 技術 | ドメイン |
| --- | --- |
| Adobe Analytics ドメイン | `adobe.com`、`adobe.net`、`adobe.io` |
| Adobe Analytics レガシードメイン | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft®Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe CX Enterprise ドメイン

Adobe CX Enterpriseでは、上記のドメインに加えて、データの収集とレポートのエクスポートに複数のドメインを利用しています。 このドメインのリストについては、[CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)で使用されるドメインを参照してください。

>[!MORELIKETHIS]
>
>Adobe Analyticsで使用される[IP アドレス ](ip-addresses.md)
>
>CX Enterpriseで使用されている[ ドメイン ](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
