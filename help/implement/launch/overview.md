---
title: Adobe Experience Platformでのタグを使用した実装
description: タグを使用したAdobe Analyticsの実装方法を説明します
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 47%

---

# Adobe Experience Platformでのタグを使用した実装

>[!NOTE]
>Adobe Experience Platform Launchは、Experience Platformのデータ収集テクノロジーのスイートとしてリブランドされました。 その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。 用語の変更点の一覧については、次の[ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)を参照してください。

Adobe Analytics が発表されて以来、アドビでは、データ収集用にサイトにコードを実装する様々な方法を提供してきました。Adobeの現在の推奨メソッドは、Adobe Experience Platformのタグを使用した方法です。

Adobe Experience Platformのタグは、他のタグ要件と共にAnalyticsコードを導入できるタグ管理ソリューションです。 アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。

アクティブなAdobe Experience Cloud契約を締結しているすべてのお客様がタグを使用できます。 Launch にアクセスできるかどうかがわからない場合は、組織の Experience Cloud システム管理者にお問い合わせください。

## ワークフロー全体

タグを使用して実装を実行するには、次の手順に従います。

1. **タグへのアクセス権を取得**:Platformタグへのアクセスは、組織のシステム管理者から取得できます。
2. **タグプロパティを作成します**。プロパティは、タグ管理データを参照するために使用される包括的なコンテナです。
3. **開発環境にデプロイ**：タグの開発を繰り返し実行できる環境を構築します。
4. **検証して実稼動環境に公開**：すべてが機能していることを確認し、公開します。

開始するには、[Analyticsタグプロパティ](create-analytics-property.md)の作成を参照してください。

## その他のリソース

タグは高度にカスタマイズできます。 実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

* [タグのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en#):インターフェイスの仕組みと使用可能な拡張機能について説明します。
* [Adobe Analytics 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en)：Analytics 拡張機能を使用して、Adobe Analytics にデータを送信します。
* [実装変数](../vars/overview.md)：データ収集サーバーに送信する変数を決定します。
