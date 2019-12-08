---
description: Adobe Analytics は様々な方法で導入できます。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;javascript
title: 実装方法の選択
topic: Developer and implementation
uuid: 20d3317f-7c63-4421-93e0-fff60dbd9f87
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 実装方法の選択

Adobe Analytics は様々な方法で導入できます。

* [!UICONTROL Adobe Experience Platform Launch]（推奨）
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch] {#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] は、アドビが提供する次世代型の Web サイトタグおよびモバイル SDK の管理機能です。[!UICONTROL Experience Platform Launch] は、顧客体験の実現に必要なすべての分析、マーケティングおよび広告の統合をデプロイおよび管理するためのシンプルな手段を提供します。

[!UICONTROL Experience Platform Launch] を利用すると、拡張と呼ばれる [!DNL Experience Platform Launch] との独自の統合を誰でも作成および管理できます。これらの拡張は、Web およびモバイルで [!UICONTROL Experience Platform Launch] をご利用のお客様自身がアプリストアで利用できるので、統合をすばやくインストール、設定およびデプロイできます。

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] では、[!DNL Analytics] の導入に伴う細かい作業の大部分を自動化できます。フォームベースのインターフェイスに必要な情報を入力すると、ページに追加する必要があるコードが [!DNL Dynamic Tag Management] によって生成されます。JavaScript に精通し、次のような基本的な Analytics の基本用語を理解するのに便利です。

* [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) の概要と仕組み
* カスタムイベントを使用す [るタイミング](/help/implement/analytics-terminology-basics/c-props-evars/event-custom.md)

Dynamic Tag Management にアクセスする方法と利用開始方法については、Dynamic Tag Management 製品ドキュメントの[はじめに](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)を参照してください。

詳しくは、「[Dynamic Tag Management を使用した Analytics の実装](/help/implement/c-implement-with-dtm/dtm-implementation-overview.md)」を参照してください。

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

JavaScript による導入方法では、ページで手動で JavaScript コードを設定する必要があります。Experience Platform Launch または Dynamic Tag Management 実装メソッドを使用する場合は、この作業の大部分を簡素化できます。ただし、場合によっては JavaScript による導入方法が必要になります。

JavaScript による導入での必要事項は次のとおりです。

* JavaScript の高いスキル
* Analytics の概念と用語に関する詳細な知識

詳しくは、「[JavaScript を使用した Analytics の実装](/help/implement/js-implementation/javascript-implementation-overview.md)」を参照してください。
