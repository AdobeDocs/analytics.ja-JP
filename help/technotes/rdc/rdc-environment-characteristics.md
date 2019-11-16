---
title: RDC 環境特性
description: null
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# RDC環境の特性

地域データ収集(RDC)環境には、次に示す特徴が含まれます。

## パフォーマンスの向上

RDCを使用する場合の現在の応答時間については、 [Adobe Analyticsリクエストのパフォーマンスを参照してください](https://marketing.adobe.com/resources/help/en_US/whitepapers/performance/)。

一般に、ユーザーは次のようにRDCで応答時間が改善されています。

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

## セキュリティで保護されているページ

サイトにhttpsプロトコルを使用するページが含まれている場合は、セキュリティで保護されたページが存在します。 Adobe Analyticsで追跡されるページビューのほとんどは、httpsプロトコルを使用して保護されます。 セキュリティで保護されたページをトラッキングするには、SSL 証明書が必要となります。WebプロパティでサードパーティCookieを使用している場合、セキュアページではアドビが所有するSSL証明書が使用され、FPSSL実装を使用せずにデータを安全にデータ収集サーバーに送信できます。

## DNS 変更（CNAME の変更）

[CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) の変更とは、社内でお使いの DNS サーバーに対する変更作業の一種です。通常、この作業は社内の IT 部門やネットワーク運用担当部署によって実施されます。この作業が必要な移行シナリオに該当する場合は、カスタマーケアにお問い合わせの上、アドビの新しいホスト名を入手してください。
