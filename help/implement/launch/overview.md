---
title: Analytics 拡張機能を使用した Adobe Analytics の実装
description: タグと Analytics 拡張機能を使用した Adobe Analytics の実装方法について説明します
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/bnn0eqUbhHvQL2YPd1qVa9cSWWvGbAAae33IyC-w9kA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 396
ht-degree: 69%

---

# Analytics 拡張機能を使用した Adobe Analytics の実装

Adobe Analytics が発表されて以来、アドビでは、データ収集用にサイトにコードを実装する様々な方法を提供してきました。 Adobeの現在のお勧めメソッドは、Adobe Experience Platformの[&#x200B; タグ &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja)を通じて使用できます。

Adobe Experience Platform のタグは、他のタグ要件と共に Analytics コードを導入できるタグ管理ソリューションです。 アドビは他のソリューションや製品との統合を提供し、カスタムコードの導入に対応します。 これらのタスクはすべて、組織の開発チームに依存せずに実行できるので、自らサイト上のコードを更新できます。

アクティブなAdobe CX Enterprise契約を持つすべてのお客様は、タグを使用できます。 アクセス権があるかどうかわからない場合は、組織のCX Enterprise システム管理者にお問い合わせください。

実装タスクの大まかな概要：



![この節の説明に従って、Analytics拡張機能ワークフローを使用してAdobe Analyticsを実装する方法。](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td> 1</td>
<td><b>レポートスイートを定義</b>したことを確認します。</td>
<td><a href="../../admin/tools/manage-rs/report-suites-admin.md">レポートスイートマネージャー</a></td>
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
<td><b><b> タグプロパティを作成</b>。 プロパティは、タグ管理データを参照するために使用される包括的なコンテナです。</td>
<td><a href="../launch/create-analytics-property.md">Adobe Analytics タグプロパティの作成</a></td>
</tr>

<tr>
<td>4</td><td>タグプロパティに <b>Analytics 拡張機能をインストールします</b>。 Analytics 拡張機能を設定して、Adobe Analytics にデータを送信します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=ja">Adobe Analytics 拡張機能の概要</a></td>
</tr>

<tr>
<td>5</td>
<td><b>開発環境にデプロイ </b>。 タグ開発を繰り返し実行できる環境を整えましょう。</td>
<td><a href="./deploy-dev.md">開発環境への Analytics 実装のデプロイ</td>
</tr>

<tr>
<td>6</td> 
<td><b>検証して実稼動環境に公開します</b>。 タグプロパティをweb サイトページに含めるコードを埋め込みます。 次に、データ要素、ルールなどを使用して、実装をカスタマイズします。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=ja#embed-code">埋め込みコード </a><br/><a href="./validate-publish-prod.md">開発実装を検証し、実稼動環境に公開</a></td>
</tr>

</table>

## その他のリソース

タグは高度にカスタマイズできます。 実装に適切なデータを含めることで Adobe Analytics を最大限に活用する方法について説明します。

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)：インターフェイスの仕組みと使用可能な拡張機能について説明します。

- [実装変数](../vars/overview.md)：データ収集サーバーに送信する変数を決定します。
