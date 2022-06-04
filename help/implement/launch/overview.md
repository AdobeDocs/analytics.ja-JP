---
title: Adobe Experience Platformでのタグ付きAdobe Analyticsの実装
description: タグを使用した Adobe Analytics の実装方法を説明します
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: 99fc7814eaa12d0d9e8e478629a4c2134a577aaa
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 94%

---

# Adobe Experience Platformでのタグ付きAdobe Analyticsの実装

Adobe Analytics が発表されて以来、アドビでは、データ収集用にサイトにコードを実装する様々な方法を提供してきました。アドビが現在推奨するのは、Adobe Experience Platform のタグを介した方法です。

Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。

有効な Adobe Experience Cloud 契約を締結しているすべてのお客様は、タグを使用できます。Launch にアクセスできるかどうかがわからない場合は、組織の Experience Cloud システム管理者にお問い合わせください。

## ワークフロー全体

タグを使用して実装を実行するには、次の手順に従います。

1. **タグへのアクセス権を取得**：Platform のタグへのアクセス権は、組織のシステム管理者から取得できます。
2. **タグプロパティを作成**：プロパティは、タグ管理データを参照するために使用される包括的なコンテナです。
3. **開発環境にデプロイ**：タグの開発を繰り返し実行できる環境を構築します。
4. **検証して実稼動環境に公開**：すべてが機能していることを確認し、公開します。

開始するには、[Analytics タグプロパティの作成](create-analytics-property.md)を参照してください。

## その他のリソース

タグは高度にカスタマイズできます。実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

* [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja)：インターフェイスの仕組みと使用可能な拡張機能について説明します。
* [Adobe Analytics 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=ja)：Analytics 拡張機能を使用して、Adobe Analytics にデータを送信します。
* [実装変数](../vars/overview.md)：データ収集サーバーに送信する変数を決定します。
