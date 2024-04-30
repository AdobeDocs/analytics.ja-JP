---
title: Adobe Analytics が使用する IP とドメイン
description: 組織のファイアウォールで、アドビから派生する IP アドレスがブロックされている場合は、このリストを使用してファイアウォール設定を更新してください。
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: ea859717c6a40b4eeeb9eca54b95718859af9c7b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 32%

---

# Adobe Analytics が使用する IP とドメイン

一部のファイアウォール設定は、Adobe Analyticsが製品インターフェイスに使用するドメインをブロックします。 このドメインのリストを使用して組織のネットワーク設定を変更し、組織内からの製品アクセスを許可できます。

## 依存する技術ドメインを許可する

Adobe Analytics では、次のホストを使用して、パフォーマンスと製品のエクスペリエンスを向上させます。Adobeでは、Adobe Analyticsを使用する最適なエクスペリエンスのために、組織のファイアウォールを通じてこれらのドメインを許可することをお勧めします。

| 技術 | ドメイン |
| --- | --- |
| Adobe Analytics ドメイン | `adobe.com`、`adobe.net`、`adobe.io` |
| Adobe Analytics レガシードメイン | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft Azure Blob ストレージ | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloudの IP アドレスブロック

上記のドメインに加えて、Adobe Analyticsでは、データ収集とレポートの書き出しに複数の IP アドレスブロックを使用します。

IP 範囲の完全なリストについては、Adobe Experience Cloud IP アドレスを参照してください。

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
