---
title: Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装
description: Adobe Experience Platform データ収集の Web SDK 拡張機能を使用して、Adobe Analytics にデータを送信します。
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 31%

---

# Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) を使用して、データを Adobe Analytics に送信できます。この実装を機能させるには、[Experience Data Model（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を Analytics で使用される形式に変換します。

Web SDK を使用して、またはタグの Web SDK 拡張機能を通じて、Experience Edge にデータを直接送信できます。

## Web SDK

実装タスクの概要です。

![Web SDK ワークフローを使用したAdobe Analyticsの実装](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td>
<td>次の条件を満たしていることを確認します。 <b>レポートスイートの定義</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td>
<td><b>スキーマとデータセットの設定</b>. Adobe Experience Platformを利用するアプリケーション間で使用するデータ収集を標準化するために、Adobeはオープンで公式に文書化された標準である Experience Data Model(XDM) を作成しました。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja">スキーマ UI の概要</a> および <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja">データセット UI の概要</a></td>
</tr>

<tr>
<td>3</td>
<td><b>データレイヤーの作成</b> を使用して、web サイト上のデータのトラッキングを管理します。</td>
<td><a href="../../prepare/data-layer.md">データレイヤーの作成</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>事前にビルドされたスタンドアロンバージョンのインストール</b>. ライブラリ (<code>alloy.js</code>) をページ上で直接 CDN に送信するか、独自のインフラストラクチャ上でダウンロードおよびホストします。 または、NPM パッケージを使用することもできます。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version">事前にビルドされたスタンドアロンバージョンのインストール</a> および <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package">NPM パッケージの使用</a></td>
</tr>

<tr>
<td>5</td>
<td><b>データストリームの設定</b>. datastream は、Adobe Experience Platform Web SDK を実装する際のサーバー側の設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">データストリームの設定<a></td> 
</tr>

<td>6</td>
<td><b>Adobe Analyticsサービスの追加</b> をデータストリームに追加します。 このサービスは、データをAdobe Analyticsに送信するかどうかと方法を制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Adobe Analyticsサービスをデータストリームに追加する</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Web SDK の設定</b>. 手順 4 でインストールしたライブラリが、データストリーム ID（旧称：エッジ設定 ID）を使用して正しく設定されていることを確認します (<code>edgeConfigId</code>)、組織 id (<code>orgId</code>) やその他の使用可能なオプションが含まれます。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja">Web SDK の設定</a></td>
</tr>

<tr>
<td>8</td>
<td><b>コマンドを実行</b> および/または <b>イベントの追跡</b>. Web ページにベースコードが実装されたら、SDK を使用してコマンドの実行とイベントの追跡を開始できます。
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en">コマンドを実行</a> および <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en">イベントの追跡</a></td>
</tr>

<tr>
<td>9</td><td><b>実装を拡張および検証する</b> 実稼動環境にプッシュする前に</td><td></td> 
</tr>
</table>


## Web SDK 拡張機能

実装タスクの概要です。

![Web SDK 拡張機能を使用したAdobe Analyticsの実装ワークフロー](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td>
<td>次の条件を満たしていることを確認します。 <b>レポートスイートの定義</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td>
<td><b>スキーマとデータセットの設定</b>. Adobe Experience Platformを利用するアプリケーション間で使用するデータ収集を標準化するために、Adobeはオープンで公式に文書化された標準である Experience Data Model(XDM) を作成しました。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja">スキーマ UI の概要</a> および <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja">データセット UI の概要</a></td>
</tr>

<tr>
<td>3</td>
<td><b>データレイヤーの作成</b> を使用して、web サイト上のデータのトラッキングを管理します。</td>
<td><a href="../../prepare/data-layer.md">データレイヤーの作成</a></td>
</tr>

<tr>
<td>4</td>
<td><b>データストリームの設定</b>. datastream は、Adobe Experience Platform Web SDK を実装する際のサーバー側の設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">データストリームの設定<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Adobe Analyticsサービスの追加</b> をデータストリームに追加します。 このサービスは、データをAdobe Analyticsに送信するかどうかと方法を制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Adobe Analyticsサービスをデータストリームに追加する</a></td>
</tr>

<tr>
<td>6</td>
<td><b>タグプロパティの作成</b>.プロパティは、タグ管理データを参照するために使用される包括的なコンテナです。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web">Web 用のタグプロパティの作成または設定</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Web SDK 拡張機能のインストールと設定</b> をタグプロパティに追加します。 手順 4 で設定したデータストリームにデータを送信するように Web SDK 拡張機能を設定します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en">Adobe Experience Platform Web SDK 拡張機能の概要</a></td>
</tr>

<tr>
<td>8</td>
<td><b>反復、検証、および公開</b> を実稼動環境に移行します。 タグプロパティを Web サイトに追加します。 その後、データ要素やルールなどを使用して、実装をカスタマイズします。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja">公開の概要</a></td>
</tr>

</table>


## その他のリソース

タグは高度にカスタマイズできます。実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)：インターフェイスの仕組みと使用可能な拡張機能について説明します。

- [Adobe Experience Platform Web SDK ドキュメント](https://experienceleague.adobe.com/docs/web-sdk.html?lang=ja)
