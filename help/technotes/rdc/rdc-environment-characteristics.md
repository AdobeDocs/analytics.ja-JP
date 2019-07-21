---
title: RDC 環境特性
seo-title: Adobe Analytics RDC環境特性
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# RDC環境の特性

地域データ収集（RDC）環境には、以下のような特性が含まれています。

## パフォーマンスの向上

For current response times when using RDC, see [Adobe Analytics Request Performance](https://marketing.adobe.com/resources/help/en_US/whitepapers/performance/).

一般に、RDCの応答時間の改善は次のようになります。

| 地域 | RDC による応答時間短縮率 |
| --- | --- |
| アジア | 36% |
| オーストラリア | 5％ |
| 中国、ロシア | 41% |
| 日本 | 41% |
| ヨーロッパ | 83% |
| ブリテン諸島 | 94% |
| 中央ヨーロッパ、東ヨーロッパ | 84% |
| 北ヨーロッパ | 73% |
| 西ヨーロッパ | 89% |
| 北アメリカ | 38% |
| カナダ | 26% |
| 米国中部 | 48% |
| 米国東部 | 46% |
| 米国西部 | 20% |
| グローバル | 50% |

## ファーストパーティCookieまたはサードパーティCookie

既存のサイトは、ファーストパーティ Cookie を使って実装されている場合と、サードパーティ Cookie を使って実装されている場合があります。ファーストパーティ Cookie について詳しくは、[こちら](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_overview.html)を参照してください。

## セキュリティで保護されたページ

サイトにhttpsプロトコルを使用するページが含まれている場合、ページはセキュリティで保護されています。Adobe Analyticsによって追跡されるページビューのほとんどは、httpsプロトコルを使用して保護されます。セキュリティで保護されたページをトラッキングするには、SSL 証明書が必要となります。WebプロパティでサードパーティCookieを使用している場合、セキュリティで保護されたページではアドビが所有するSSL証明書を使用します。これにより、FPSSL実装なしでデータ収集サーバーに安全にデータを送信できます。

## DNS 変更（CNAME の変更）

[CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) の変更とは、社内でお使いの DNS サーバーに対する変更作業の一種です。通常、この作業は社内の IT 部門やネットワーク運用担当部署によって実施されます。この作業が必要な移行シナリオに該当する場合は、カスタマーケアにお問い合わせの上、アドビの新しいホスト名を入手してください。
