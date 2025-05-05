---
title: Analytics 拡張機能を使用した Adobe Analytics の実装
description: タグと Analytics 拡張機能を使用した Adobe Analytics の実装方法について説明します
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 83%

---

# Analytics 拡張機能を使用した Adobe Analytics の実装

Adobe Analytics が発表されて以来、アドビでは、データ収集用にサイトにコードを実装する様々な方法を提供してきました。Adobeが現在推奨するのは、Adobe Experience Platformの [ タグ ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja) を使用する方法です。

Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。

有効なAdobe Experience Cloud契約を締結しているすべてのお客様は、タグを使用できます。 Launch にアクセスできるかどうかがわからない場合は、組織の Experience Cloud システム管理者にお問い合わせください。

実装タスクの大まかな概要：



![ この節で説明しているように、Analytics 拡張機能ワークフローを使用してAdobe Analyticsを実装する方法 ](../assets/analytics-extension-annotated.png)

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
<td><a href="../launch/create-analytics-property.md">Adobe Analytics タグプロパティの作成</a></td>
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
<td><b>検証して実稼動環境に公開します</b>。タグプロパティを web サイトページに含めるためのコードを埋め込みます。 次に、データ要素、ルールなどを使用して、実装をカスタマイズします。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=ja#embed-code"> 埋め込みコード </a><br/><a href="./validate-publish-prod.md"> 開発実装の検証と実稼動環境への公開 </a></td>
</tr>

</table>

## その他のリソース

タグは高度にカスタマイズできます。実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)：インターフェイスの仕組みと使用可能な拡張機能について説明します。

- [実装変数](../vars/overview.md)：データ収集サーバーに送信する変数を決定します。
