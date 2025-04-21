---
description: Adobe Analytics 1.4 API の提供終了のお知らせの詳細。
title: Adobe Analytics 1.4 API EOL FAQ
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 4%

---

# Adobe Analytics 1.4 API EOL FAQ

Adobeは、Adobe Analytics 1.4 API を **2026 年 8 月 12 日** に廃止する予定です。 この日付を過ぎるとアクセスできなくなります。 このお知らせは、次の内容に直接影響します。

* Adobe Analytics 1.4 API （Data Insertion API を除く）
* Adobe Analytics WSSE 認証

## 1.4 API

[Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/) は、レポート、分類、データフィード、レポートスイート設定など、様々なアクションを提供します。 これらは、[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に置き換わろうとしています。 2.0 API を使用すると、セグメントや計算指標などのコンポーネントのレポートや管理など、Analytics ユーザーインターフェイスで実行できるほぼすべてのアクションを実行できます。

Adobeは、1.4 API ユーザー向けに [ 移行パス ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) を提供しています。 統合を 2.0 API （Adobe Analytics アプリケーションが依存するのと同じ API）に移行し、最新の機能を活用できます。 1.4 API で使用できる機能は、[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) を使用して実現できます。

## WSSE 認証

WSSE 認証は、Analytics 1.4 API でサポートされるレガシー認証プロトコルです。 これは、[Adobe Developer Console](https://developer.adobe.com/console/home) で提供される OAuth ベースの認証オプションに置き換えられました。 WSSE 認証を使用するプロジェクトでは、資格情報をAdobe Developer Consoleでプロビジョニングされた資格情報に更新する必要があります。 これを行うには、[Adobe Developer Console](https://developer.adobe.com/console/home) にログインして、Analytics 2.0 API 統合用のプロジェクトを作成します。 OAuth ユーザー認証方法または OAuth サーバー間認証方法のいずれかを選択します。

## FAQ

+++**これは、Analytics API の既存のAdobe IO プロジェクトに影響しますか？**

Analytics 1.4 API を使用している既存のプロジェクトが影響を受けます。 これらの統合は、EOL 期日の前に [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があります。

+++

+++**Analytics API を使用する別の製品やアプリケーションと、Adobeの資格情報を共有しました。 影響の有無**

その製品またはアプリケーションが WSSE 資格情報を使用したり、Analytics 1.4 API を呼び出したりすると、影響を受けるため、EOL 期限の前に移行する必要があります。 移行プランとタイムラインについて詳しくは、製品またはアプリケーションプロバイダーにお問い合わせください。

+++

+++**プロジェクトで使用する API を確認するにはどうすればよいですか？**

API が呼び出すベース URL によって、プロジェクトで使用する API バージョンが決まります。 Adobe Analytics 1.4 API では、次の URL を使用します。
* `https://api.omniture.com`
* `https://api3.omniture.com`
* `https://api4.omniture.com`
* `https://api5.omniture.com`

[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) は次の URL を使用します：

* `https://analytics.adobe.io`

API プロジェクトのいずれかで `api*.omniture.com` を使用している場合は、Adobe Analytics 1.4 API を使用し、2.0 API に移行する必要があります。

+++

+++**提供終了はデータ収集に影響を与えますか？**

Adobe Analytics 1.4 の EOL は、タグ（タグ（旧称：Adobe Launch）、Web SDK、AppMeasurementなど）のタグソリューションには影響しません。 ただし、1.4 Data Sources API または Classifications API を使用してデータを強化する場合は、これらのワークフローをAdobe Analytics 2.0 API に移行する必要があります。

Data Insertion API は、この提供終了のお知らせの影響を受けません。 Adobeは Data Insertion API のサポートを引き続き提供する予定ですが、Adobeでは [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) を代わりに使用することをお勧めします。

+++

この提供終了のお知らせについて、このページに記載されていないその他の質問がある場合は、Adobe アカウントチームにお問い合わせください。
