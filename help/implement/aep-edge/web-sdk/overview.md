---
title: Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装
description: Adobe Experience Platform データ収集の Web SDK 拡張機能を使用して、Adobe Analytics にデータを送信します。
source-git-commit: e6b40881a543b43c03b612c7e7b0d9bd09f44c0d
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 24%

---

# Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) を使用して、データを Adobe Analytics に送信できます。この実装を機能させるには、[Experience Data Model（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を Analytics で使用される形式に変換します。

Web SDK を使用して、またはタグの Web SDK 拡張機能を通じて、Experience Edge にデータを直接送信できます。

## Web SDK

実装タスクの概要です。

![Web SDK ワークフローを使用したAdobe Analyticsの実装](../../assets/websdk-annotated.png)

|<div style="width:20px"></div>|タスク |詳細情報 | |-| —|—| | 1 |以下をお持ちであることを確認してください： **レポートスイートの定義**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **スキーマとデータセットの設定**. Adobe Experience Platformを利用するアプリケーション間で使用するデータ収集を標準化するために、Adobeはオープンで公式に文書化された標準である Experience Data Model(XDM) を作成しました。 | [スキーマ UI の概要](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja) および [データセット UI の概要](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja) | | 3 | **データレイヤーの作成** を使用して、web サイト上のデータのトラッキングを管理します。 | [データレイヤーの作成](../../prepare/data-layer.md) | | 4 | **事前にビルドされたスタンドアロンバージョンのインストール**. ライブラリ (`alloy.js`) をページ上で直接 CDN に送信するか、独自のインフラストラクチャ上でダウンロードおよびホストします。 または、NPM パッケージを使用することもできます。 | [事前にビルドされたスタンドアロンバージョンのインストール](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) および [NPM パッケージの使用](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package)| | 5 | **データストリームの設定**. datastream は、Adobe Experience Platform Web SDK を実装する際のサーバー側の設定を表します。 | [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 6 | **Adobe Analyticsサービスの追加** をデータストリームに追加します。 このサービスは、データをAdobe Analyticsに送信するかどうかと方法を制御します。 | [Adobe Analyticsサービスをデータストリームに追加する](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 7 | **Web SDK の設定**. 手順 4 でインストールしたライブラリが、データストリーム ID（旧称：エッジ設定 ID）を使用して正しく設定されていることを確認します (`edgeConfigId`)、組織 id (`orgId`) やその他の使用可能なオプションが含まれます。 | [Web SDK の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja) | | 8 | **コマンドを実行** および/または **イベントの追跡**. Web ページにベースコードが実装されたら、SDK を使用してコマンドの実行とイベントの追跡を開始できます。 | [コマンドを実行](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en) および [イベントの追跡](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en) | | 9 | **実装を拡張および検証する** 実稼動環境にプッシュする前に | |



## Web SDK 拡張機能

実装タスクの概要です。

![Web SDK 拡張機能を使用したAdobe Analyticsの実装ワークフロー](../../assets/websdk-extension-annotated.png)

|<div style="width:20px"></div> |タスク |詳細情報 | |-| —|—| | 1 |以下をお持ちであることを確認してください： **レポートスイートの定義**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **スキーマとデータセットの設定**. Adobe Experience Platformを利用するアプリケーション間で使用するデータ収集を標準化するために、Adobeはオープンで公式に文書化された標準である Experience Data Model(XDM) を作成しました。 | [スキーマ UI の概要](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja) および [データセット UI の概要](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja) | | 3 | **データレイヤーの作成** を使用して、web サイト上のデータのトラッキングを管理します。 | [データレイヤーの作成](../../prepare/data-layer.md) | | 4 | **データストリームの設定**. datastream は、Adobe Experience Platform Web SDK を実装する際のサーバー側の設定を表します。 | [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 5 | **Adobe Analyticsサービスの追加** をデータストリームに追加します。 このサービスは、データをAdobe Analyticsに送信するかどうかと方法を制御します。 | [Adobe Analyticsサービスをデータストリームに追加する](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 6 | **タグプロパティの作成**. プロパティは、タグ管理データを参照するために使用される包括的なコンテナです。| [Web 用のタグプロパティの作成または設定](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web) | | 7 | **Web SDK 拡張機能のインストールと設定** をタグプロパティに追加します。 手順 4 で設定したデータストリームにデータを送信するように Web SDK 拡張機能を設定します。 | [Adobe Experience Platform Web SDK 拡張機能の概要](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en) | | 8 | **反復、検証、および公開** を実稼動環境に移行します。 タグプロパティを Web サイトに追加します。 その後、データ要素やルールなどを使用して、実装をカスタマイズします。 | [パブリッシュの概要](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja) |



## その他のリソース

タグは高度にカスタマイズできます。実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)：インターフェイスの仕組みと使用可能な拡張機能について説明します。

- [Adobe Experience Platform Web SDK ドキュメント](https://experienceleague.adobe.com/docs/web-sdk.html?lang=ja)
