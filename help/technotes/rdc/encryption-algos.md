---
title: サポートされる HTTPS 暗号化アルゴリズム
description: 2022 年 6 月 23 日に、暗号セキュリティレベルを「高」に設定したお客様に対し、SHA1 または CBC を利用した TLS 1.2 暗号のサポートを削除します。
feature: Regional Data Collection
source-git-commit: ce607610516a94e4d0fbbc53a1f8f53f5977a777
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# サポートされる HTTPS 暗号化アルゴリズム

Adobeは、ファーストパーティのデータ収集に関するセキュリティに関する様々なお客様のニーズに応える 2 種類の暗号セキュリティレベルを提供します。 これらのレベルは、サーバーとの HTTPS 接続でサポートされる暗号化アルゴリズムを決定します。 お客様のデフォルトは「標準」で、最新の暗号化アルゴリズムのみがサポートされています。 「High」は、これらの接続をより重視するお客様向けに、より小さい暗号化アルゴリズムのリストをサポートします。 両方のセキュリティレベルで、Adobeは、現在のセキュリティ慣行に基づいて、サポートされているアルゴリズムのセットを定期的に更新します。 暗号セキュリティ設定を変更したい場合は、カスタマーケアにお問い合わせください。

2022 年 6 月 23 日に、暗号セキュリティレベルを「高」に設定したお客様に対し、SHA1 または CBC を利用した TLS 1.2 暗号のサポートを削除します。  この変更は、古いオペレーティングシステムでのエンドユーザーの安全なデータ収集に影響します。

次の TLS 1.2 暗号はサポートされなくなります。

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

次のクライアントは、現在の暗号化標準をサポートしていないため、この変更の影響を受けることが知られています。

* Windows 8.1 以前（2018 年最終更新）
* Windows Phone 8.1 以前（2016 年最終更新）
* OS X 10.10 以前（2017 年の最終更新）
* iOS 8.4 以前（2015 年最終更新）

Android デバイスは、この変更による影響を受けません。

暗号セキュリティレベルが「標準」に設定されているお客様は、この変更による影響を受けません。
