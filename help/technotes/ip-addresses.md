---
title: Adobe Analyticsで使用される IP アドレス
description: 組織のファイアウォールで、アドビから派生する IP アドレスがブロックされている場合は、このリストを使用してファイアウォール設定を更新してください。
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 5ac6da2eb53d2748e8838ef2c6334a771abc26c9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 35%

---

# Adobe Analyticsで使用される IP アドレス

一部のファイアウォール構成では、アドビのデータ収集サーバーまたはデータにアクセスするためのサーバーの IP アドレスをブロックするものがあります。このリストの範囲を使用して、組織のファイアウォール設定を変更し、アクセスを許可したり、組織内からデータを送信したりできます。

Adobe Analyticsで使用される IP アドレスは、China Performance Optimization アドオンパッケージを除き、すべて [Adobe Experience Cloudで使用される IP アドレス ](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/ip-addresses) の一部です。

## 中国のパフォーマンス最適化 IP アドレス

China Performance Optimization アドオンパッケージは、中国国内の訪問者のAppMeasurementデータ収集パフォーマンスを向上させる有料サービスです。 この機能の使用方法について詳しくは、Adobeアカウントチームにお問い合わせください。

>[!IMPORTANT]
>
>中国の RDC は、Web SDK データ収集には使用できません。 これらのサーバは、AppMeasurement ライブラリにのみ適用されます。

中国の地域データ収集サーバーは、次の IP アドレスを使用します。

| 場所 | ホスト |
| --- | --- |
| 中国 | `52.80.168.159` |
| 中国 | `52.80.199.104` |
| 中国 | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>[Adobe Experience Cloudで使用される IP アドレス ](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/ip-addresses)
>
>[Adobe Analyticsが使用するドメイン ](domains.md)
