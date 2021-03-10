---
title: DFA統合 — 提供終了情報
description: AdobeがDFA Data Connectorの提供終了と代替手段を提供するのはなぜですか。
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# DFA統合 — 提供終了情報

Adobeは最近、[提供終了のData Connector](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html)の計画を発表しました。これは、サードパーティデータを統合するための従来のツールセットです（ESP、VOCなど）。 Adobe Analyticsと

## Data Connectorsが提供終了になる理由

パートナー統合でサポートされるプラットフォームは[Adobe交換](https://exchange.adobe.com/experiencecloud)です。Digital Experience Application Integration、サードパーティCXM統合を容易にし、将来的にクライアントとパートナーの様々なデータ要件をサポートするように設計されています。 Data Connectorsを使用して統合を構築した多くのパートナーは、既にこれらの統合をAdobeExchangeに移行しており、その移行を計画しているパートナーも増えています。

## DFA統合が提供終了になるのはなぜですか。

[2020年1月、Googleは、2022年までにChromeのサードパーティcookieを廃止すると](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html)発表しました。 これは、AppleとMozillaがそれぞれSafariとFirefoxのブラウザに対して設定した業界標準に従っています。 DFA統合は、サードパーティcookieに大きく依存しているため、3つの主要なインターネットブラウザーでサードパーティcookieを削除することで、効果がなくなり、古くなります。 Google [は2021年3月](https://blog.google/products/ads-commerce/a-more-privacy-first-web)に、別の解決策を発表しないと発表し、この姿勢を強化した。

残念ながら、DFA統合を所有するGoogleは、GoogleをAdobeExchangeプラットフォームに複製する可能性は低くなります。 したがって、Data Connectorsがオフラインになると、既存の統合が機能しなくなり、製品化された置き換えが行われなくなることを前提として、今後の作業を進めていきます。

重要で追加的な要因は、DFA統合の「表示スルー」機能です。 これにより、Adobe Analyticsはディスプレイ広告を見たユーザがクリックせず、その後Webサイトを訪問した場合を追跡できます。 「表示スルー」はサードパーティcookieに基づいており、2021年中に廃止され続けます。 これは、Adobeの問題だけでなく、市場全体にわたる問題です。 現時点では、このデータを複製する代替手段はありません。

## 君には何の代替案がある？

ディスプレイ広告データ(「表示スルー」なし)をAdobe Analyticsに統合したいお客様のために、現在、次のオプションを用意しています。

* Adobe Advertising Cloud DSPのお客様は、Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations)との製品化された統合を活用して、GoogleからAdobe Analyticsにディスプレイ広告データを設定できます。 [この統合はアドビの最善の代替手段であり、お客様にお勧めします。 Ad CloudのDSPでは、有料検索、ディスプレイ、ビデオなど、すべての広告チャネルにわたって接続されたエクスペリエンスを提供できます。 詳しくは[こちら](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction)。ただし、Ad CloudDSPは、サードパーティcookieが失われた場合にも影響を受けます。
* Adobe Experience Platformと[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en)。他のデータソースとのディスプレイ広告統合に関する機能を提供します。 顧客は有料検索プロバイダーから表示データをダウンロードし、Experience Platformにアップロードできます。 その後、データを直接CJAに取り込み、他のデータセットと共に分析します。
* Adobeコンサルティング（エンジニアリングアーキテクト）は、ディスプレイ広告指標をAdobe Analyticsに取り込むためのカスタムソリューションを構築できます。 このソリューションはまだ開発段階で、ベータ版に興味を持つお客様は、ぜひ参加してください。 機能、可用性、コストの詳細は、利用可能になった時点で提供されます。
* データソース機能とAdobe Analyticsの分類を使用して、独自のディスプレイ広告統合を管理できます。 データソースと分類[を使用して、有料検索をインポートし、データを手動で表示します（](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases)を参照）。 (注意：このドキュメントは有料検索を指しますが、使用事例と概念は同じで、表示に適用できます)。

その他の質問やサポートについては、[Adobeカスタマーケア](https://helpx.adobe.com/jp/contact/enterprise-support.ec.html)にお問い合わせください。