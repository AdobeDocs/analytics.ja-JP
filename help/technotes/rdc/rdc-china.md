---
title: 中国向け地域データ収集
seo-title: Adobe Analytics China RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 中国向け地域データ収集

中国大陸への Adobe の地域データ収集（RDC）導入により、中国内のお客様は世界の他の地域ではなく中国内のデータ収集センター（DCC）にデータを直接送信できるようになります。これによりページの読み込み時間とデータの精度は、中国外の DCC にデータを送信する場合と比較して向上します。

> [!IMPORTANT] 中国のRDCノードの使用に関連して、追加料金が発生します。 このドキュメントで説明するRDCノードを使用して中国でデータ収集を実装する前に、組織のアカウントマネージャーに連絡して、この機能への権利が正しく付与されていることを確認してください。

## 中国向けのトラッキングサーバーの設定

トラッキングは、サービスで都合のいい任意の時点で中国の RDC に導入できます。中国のRDCにルーティングするデジタルプロパティ（モバイルアプリやWebページなど）の場合は、トラッキングサーバーを次のように変更します。

`<namespace>.sc.adobedc.cn`

正しい名前空間を入力するようにしてください。これは通常既存のトラッキングサーバーの最初に見つかります。For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. また、SSL ではないファーストパーティの [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) レコードをこの新しい場所にポイントすることもできます。

顧客ベースの大部分が中国以外にある場合は、すべてのプロパティおよび地域に対してグローバルにtrackingServer値を中国のRDCに設定しないでください。 トラッキングサーバーは、中国内にいる顧客についてのみ中国 RDC 値に設定する必要があります。それ以外の場合、中国外のユーザーの速度に悪影響を与えます。これは、データ収集を中国に向かわせてその後応答を戻させるためです。

## 中国のユーザーの識別

デジタルプロパティがどこでホストされているか、またどの言語が使用されているかに関わらず、中国で RDC ノードを使用すれば中国内のユーザーエクスペリエンスは改善されます。そのため、推奨の実践は、どのユーザーが中国にいるのかを判断した後にそれらのユーザーに中国の RDC を使用することです。これらのユーザーを特定するのに役立つ方法には次のものがあります。

* 信頼性の高いGeoIPソリューションの使用。  Adobe Experience Platform Launch（またはData Tag Management）との統合を簡単に行うために、サーバー側のソリューションを使用することもできます。 この場合、場所は、Experience Platform LaunchまたはDTMオブジェクトに標準データ要素を含めることで判断できます。 または、クライアント側の GeoIP ソリューションを使用することもあります。この場合、エクスペリエンスプラットフォームの起動は、クライアント側コードにフックできます。 このようなソリューションには、ユーザーに翻訳されたサイトへの移動を促す必要がある場合があることにご注意ください。これは、最初のページがグローバルトラッキングサーバーによって、2番目のページが中国のページによってカウントされるリスクを示し、2回訪問が発生する可能性があります。 GeoIP ソリューションにのベストプラクティスに従ってください。アドビはご使用の GeoIP ソリューションの正確性について責任を負いません。

* Using site structure or the browser language (the `navigator.language / accept-language` header). この方法のメリットは、低コストなこととパフォーマンスが向上する可能性があることです。この方法のデメリットは、中国外で中国語を使用する訪問者の速度に悪影響を与えることです。
* 中国ベースのホスティングソリューションを使用し、ホストに基づいてtrackingServerを中国のRDCに設定します。 これはまた、速度を大幅に向上させます。

## 現在の制限

中国のRDCの現在の制限：

1. 中国のRDCは、ファーストパーティSSL([JavaScriptでは](https://helpx.adobe.com/analytics/kb/determining-data-center.html) s.trackingServerSecure [](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) )またはAdobe Audience Managerへのサーバー側転送をサポートしていません。
2. [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) と [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/) はサポートされているものの、ターゲットと Demdex のドメインは中国大陸にはなく、中国の RDC 内と比較して速度や信頼性のメリットがありません。

## 中国に対するアドビの取り組み

アドビでは、中国の RDC を永続的に推進することを計画しており、最終的にはファーストパーティ SSL やサーバー側の転送などの機能のサポートを追加する予定です。また、中国内での ECID と Audience Manager 収集を完全にサポートするために、Demdex（または同等のもの）ドメインを中国で提供することを計画しています。アドビの中国の RDC を使用し始めたユーザーは、このデータ収集のエンドポイントを無制限で使用できます。
