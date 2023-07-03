---
title: Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装
description: Adobe Experience Platform データ収集の Web SDK 拡張機能を使用して、Adobe Analytics にデータを送信します。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
source-git-commit: d9948fbb63d44c851e08745c77af5618de84a89c
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 100%

---

# Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=ja) を使用して、データを Adobe Analytics に送信できます。この実装を機能させるには、[Experience Data Model（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を Analytics で使用される形式に変換します。

Web SDK を使用して、またはタグの Web SDK 拡張機能を通じて、Experience Edge にデータを直接送信できます。

## Web SDK

実装タスクの大まかな概要：

![Web SDK ワークフローを使用した Adobe Analytics の実装](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td>
<td><b>レポートスイートを定義</b>したことを確認します。</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td>
<td><b>スキーマとデータセットを設定します</b>。Adobe Experience Platform を活用するアプリケーション間で使用するデータ収集を標準化するために、アドビはオープンで公的に文書化された標準である Experience Data Model（XDM）を作成しました。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja">スキーマ UI の概要</a>および<a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja">データセット UI の概要</a></td>
</tr>

<tr>
<td>3</td>
<td><b>データレイヤーを作成</b>して、web サイト上のデータのトラッキングを管理します。</td>
<td><a href="../../prepare/data-layer.md">データレイヤーの作成</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>事前ビルドスタンドアロンバージョンをインストールします</b>。CDN のライブラリ（<code>alloy.js</code>）をページで直接参照するか、ダウンロードして独自のインフラストラクチャにホストすることができます。または、NPM パッケージを使用することもできます。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja#option-2%3A-installing-the-prebuilt-standalone-version">事前ビルドスタンドアロンバージョンのインストール</a>および<a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja#option-3%3A-using-the-npm-package">NPM パッケージの使用</a></td>
</tr>

<tr>
<td>5</td>
<td><b>データストリームを設定</b>します。データストリームは、Adobe Experience Platform Web SDK を実装する際のサーバーサイド設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja">データストリームの設定<a></td> 
</tr>

<td>6</td>
<td>データストリームに <b>Adobe Analytics サービス</b>を追加します。このサービスは、Adobe Analytics にデータを送信するかどうかと、どのように送信するかを制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja#analytics">データストリームへの Adobe Analytics サービスの追加</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Web SDK を設定</b>します。手順 4 でインストールしたライブラリが、データストリーム ID（以前のエッジ設定 ID（<code>edgeConfigId</code>））、組織 ID（<code>orgId</code>）、その他の使用可能なオプションで適切に設定されていることを確認します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja">Web SDK の設定</a></td>
</tr>

<tr>
<td>8</td>
<td><b>コマンドを実行</b>したり、<b>イベントを追跡</b>したりします。Web ページにベースコードが実装されたら、SDK を使用してコマンドの実行とイベントの追跡を開始できます。
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=ja">コマンドの実行</a>および<a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=ja">イベントの追跡</a></td>
</tr>

<tr>
<td>9</td><td>実装を実稼動環境にプッシュする前に、<b>実装を拡張して検証します</b>。</td><td></td> 
</tr>
</table>


## Web SDK 拡張機能

実装タスクの大まかな概要：

![Web SDK 拡張機能ワークフローを使用した Adobe Analytics の実装](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td>
<td><b>レポートスイートを定義</b>したことを確認します。</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td>
<td><b>スキーマとデータセットを設定します</b>。Adobe Experience Platform を活用するアプリケーション間で使用するデータ収集を標準化するために、アドビはオープンで公的に文書化された標準である Experience Data Model（XDM）を作成しました。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja">スキーマ UI の概要</a>および<a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja">データセット UI の概要</a></td>
</tr>

<tr>
<td>3</td>
<td><b>データレイヤーを作成</b>して、web サイト上のデータのトラッキングを管理します。</td>
<td><a href="../../prepare/data-layer.md">データレイヤーの作成</a></td>
</tr>

<tr>
<td>4</td>
<td><b>データストリームを設定</b>します。 データストリームは、Adobe Experience Platform Web SDK を実装する際のサーバーサイド設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja">データストリームの設定<a></td> 
</tr>

<tr>
<td>5</td> 
<td>データストリームに <b>Adobe Analytics サービスを追加します</b>。 このサービスは、Adobe Analytics にデータを送信するかどうかと、どのように送信するかを制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja#analytics">データストリームへの Adobe Analytics サービスの追加</a></td>
</tr>

<tr>
<td>6</td>
<td><b>タグプロパティを作成します</b>。プロパティは、タグ管理データを参照するために使用される包括的なコンテナです。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=ja#for-web">Web 用のタグプロパティの作成または設定</a></td>
</tr>

<tr>
<td>7</td> 
<td>タグプロパティに <b>Web SDK 拡張機能をインストールして設定します</b>。手順 4 で設定したデータストリームにデータを送信するように Web SDK 拡張機能を設定します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=ja">Adobe Experience Platform Web SDK 拡張機能の概要</a></td>
</tr>

<tr>
<td>8</td>
<td><b>反復し、検証して実稼動環境に公開します</b>。タグプロパティを web サイトに追加します。次に、データ要素、ルールなどを使用して、実装をカスタマイズします。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja">公開の概要</a></td>
</tr>

</table>


## その他のリソース

タグは高度にカスタマイズできます。実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)：インターフェイスの仕組みと使用可能な拡張機能について説明します。

- [Adobe Experience Platform Web SDK ドキュメント](https://experienceleague.adobe.com/docs/web-sdk.html?lang=ja)
