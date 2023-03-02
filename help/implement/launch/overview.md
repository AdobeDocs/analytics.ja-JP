---
title: Analytics 拡張機能を使用した Adobe Analytics の実装
description: タグと Analytics 拡張機能を使用した Adobe Analytics の実装方法について説明します
feature: Launch Implementation
source-git-commit: aef1d613437688b7eed704b227c41e4fbe4677dd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Analytics 拡張機能を使用した Adobe Analytics の実装

Adobe Analytics が発表されて以来、アドビでは、データ収集用にサイトにコードを実装する様々な方法を提供してきました。アドビが現在推奨するのは、Adobe Experience Platform のタグを介した方法です。

Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。

有効な Adobe Experience Cloud 契約を締結しているすべてのお客様は、タグを使用できます。Launch にアクセスできるかどうかがわからない場合は、組織の Experience Cloud システム管理者にお問い合わせください。

実装タスクの大まかな概要：



![Analytics 拡張機能ワークフローを使用した Adobe Analytics](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td> 1</td>
<td><b>レポートスイートを定義</b>したことを確認します。</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td>
<td><b>データレイヤーを作成</b>して、web サイト上のデータのトラッキングを管理します。</td>
<td>
<a href="../prepare/data-layer.md">データレイヤーの作成</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>タグプロパティを作成します</b>。プロパティは、タグ管理データを参照するために使用される包括的なコンテナです。</td>
<td><a ref="../launch/create-analytics-property.md">Adobe Analytics タグプロパティの作成</a></td>
</tr>

<tr>
<td>4</td><td>タグプロパティに <b>Analytics 拡張機能をインストールします</b>。Analytics 拡張機能を設定して、Adobe Analytics にデータを送信します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=ja">Adobe Analytics 拡張機能の概要</a></td>
</tr>

<tr>
<td>5</td>
<td><b>開発環境にデプロイします</b>。タグの開発を繰り返し実行できる環境を構築します。</td>
<td><a href="./deploy-dev.md">開発環境への Analytics 実装のデプロイ</td>
</tr>

<tr>
<td>6</td> 
<td><b>検証して実稼動環境に公開します</b>。タグプロパティを web サイトに追加します。次に、データ要素、ルールなどを使用して、実装をカスタマイズします。</td>
<td><a href="./validate-publish-prod.md">開発実装の検証と実稼動環境への公開</a></td>
</tr>

</table>

## その他のリソース

タグは高度にカスタマイズできます。実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)：インターフェイスの仕組みと使用可能な拡張機能について説明します。

- [実装変数](../vars/overview.md)：データ収集サーバーに送信する変数を決定します。
