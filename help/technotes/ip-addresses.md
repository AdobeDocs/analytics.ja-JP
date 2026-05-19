---
title: ADOBE ANALYTICSで使用されるIP アドレス
description: 組織のファイアウォールで、アドビから派生する IP アドレスがブロックされている場合は、このリストを使用してファイアウォール設定を更新してください。
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
TQID: https://experienceleague.adobe.com/-4XZdprTBXpIaFnHeXBQsAr5YoZMW4ocnZRY50bHGUs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 32%

---

# ADOBE ANALYTICSで使用されるIP アドレス

一部のファイアウォール構成では、アドビのデータ収集サーバーまたはデータにアクセスするためのサーバーの IP アドレスをブロックするものがあります。 このリストの範囲を使用して、組織のファイアウォール設定を変更し、アクセスを許可したり、組織内からデータを送信したりできます。

Adobe Analyticsで使用されるすべてのIP アドレスは、China Performance Optimization アドオンパッケージを除き、CX Enterprise[&#128279;](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)で使用されるIP アドレスの一部です。

## 中国パフォーマンス最適化IP アドレス

China Performance Optimization アドオンパッケージは、中国国内の訪問者向けにAppMeasurementのデータ収集パフォーマンスを向上させる有料サービスです。 この機能の使用方法について詳しくは、Adobe アカウントチームにお問い合わせください。

>[!IMPORTANT]
>
>China RDCは、Web SDK データ収集には使用できません。 これらのサーバーは、AppMeasurement ライブラリにのみ適用されます。

中国の地域データ収集サーバーでは、次のIP アドレスを使用します。

| 場所 | ホスト |
| --- | --- |
| 中国 | `52.80.168.159` |
| 中国 | `52.80.199.104` |
| 中国 | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>CX Enterprise[&#128279;](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)によって使用されるIP アドレス
>
>Adobe Analyticsで使用されている[&#x200B; ドメイン &#x200B;](domains.md)
