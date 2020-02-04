---
title: 起動と共に実装の概要
description: Adobe Experience Platform Launchを使用したAdobe Analyticsの実装方法を説明します。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# 起動と共に実装の概要

Adobe Analyticsの有効期間中、アドビでは、データ収集用にサイトにコードを実装する様々な方法を提供してきました。 アドビの現在の推奨方法は、Adobe Experience Platform Launchを通じてです。

Launchは、他のタグ要件と共にAnalyticsコードを導入できるtag managementソリューションです。 アドビは、他のソリューションや製品との統合を提供し、カスタムコードを導入できます。 これらのタスクはすべて、組織の開発チームに依存せずに実行し、サイト上のコードを更新できます。

有効なAdobe Experience cloud契約を締結しているすべてのお客様は、「起動」を使用できます。 アクセス権が不明な場合は、組織のExperience cloudシステム管理者に問い合わせてください。

## ワークフロー全体

「起動」を使用して実装を実行するには、次の手順に従います。

1. **Gain access to Launch**:「起動」へのアクセス権は、組織のシステム管理者から取得できます。
2. **プロパティの作成**:プロパティは、tag managementデータを参照するために使用されるオーバーカーチコンテナです。
3. **開発環境へのデプロイ**:タグの開発を繰り返し実行できる環境を構築します。
4. **検証して実稼働環境に発行**:すべてが機能していることを確認し、公開してください。

開始する [には、「Adobe Experience Platform LaunchでのAnalyticsプロパティの作成](create-analytics-property.md) 」を参照してください。

## その他のリソース

起動は高度にカスタマイズできます。 導入に適切なデータを含めることで、Adobe Analyticsを最大限に活用する方法について説明します。

* [ドキュメントの起動](https://docs.adobe.com/content/help/en/launch/using/overview.html):インターフェイスの仕組みと使用可能な拡張機能について説明します。
* [Adobe Analytics拡張機能](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html):Analytics拡張機能を使用して、Adobe Analyticsにデータを送信します。
* [実装変数](../vars/overview.md):データ収集サーバーに送信する変数を決定します。
