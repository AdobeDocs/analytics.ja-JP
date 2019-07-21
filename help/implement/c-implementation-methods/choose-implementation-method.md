---
description: Adobe Analytics は様々な方法で導入できます。
keywords: Analyticsの導入;導入方法、Dynamic Tag Management;dtm;javascript
seo-description: Adobe Analytics は様々な方法で導入できます。
seo-title: 導入方法の選択
solution: Analytics
title: 導入方法の選択
topic: 開発者と導入
uuid: 20d3317f-7c63-4421-93e0- fff60dbd9f87
translation-type: tm+mt
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# 導入方法の選択

Adobe Analytics は様々な方法で導入できます。

* [!UICONTROL Adobe Experience Platform Launch] （推奨）
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch]{#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] は、アドビからの次世代のWebサイトタグおよびモバイルSDK管理機能です。[!UICONTROL Experience Platform Launch] では、関連する顧客エクスペリエンスに必要なすべての分析、マーケティングおよび広告統合を簡単にデプロイおよび管理できます。

[!UICONTROL エクスペリエンスプラットフォーム起動] では、「拡張子」と呼ばれる独自の統合を構築して維持 [!DNL Experience Platform Launch]することができます。These extensions are available to web and mobile [!UICONTROL Experience Platform Launch] customers in an app-store experience, so customers can quickly install, configure, and deploy their integrations.

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] は、実装に必要な詳細作業の多くを自動化 [!DNL Analytics]します。フォームベースのインターフェイスに必要な情報を入力すると、ページに追加する必要があるコードが [!DNL Dynamic Tag Management] によって生成されます。これはJavaScriptに精通していて、Analyticsの基本用語を理解するのに役立ちます。例えば、

* [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) の概要と仕組み
* どのようなケースで [カスタムイベント](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)を使用すると効果的か

Dynamic Tag Management にアクセスする方法と利用開始方法については、Dynamic Tag Management 製品ドキュメントの[はじめに](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)を参照してください。

詳しくは、[Dynamic Tag ManagementによるAnalyticsの導入](../../implement/c-implement-with-dtm/dtm-implementation-overview.md)を参照してください。

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

JavaScript による導入方法では、ページで手動で JavaScript コードを設定する必要があります。この作業の多くは、Experience Platform LaunchまたはDynamic Tag Management実装方法を使用して簡単に行うことができます。ただし、場合によっては JavaScript による導入方法が必要になります。

JavaScript による導入での必要事項は次のとおりです。

* JavaScript の高いスキル
* Analytics の概念と用語に関する詳細な知識

詳しくは、[JavaScriptを使用したAnalyticsの導入](../../implement/js-implementation/javascript-implementation-overview.md)」を参照してください。
