---
title: Adobe Experience Platform Edge Network APIを使用したAdobe Analyticsの実装
description: Adobe Experience Platform Edge Network APIを使用して、Adobe Analyticsにデータを送信します。
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/lvnplKx6dPwmmbZWgSShGvZXD2TtUoigi-HNiKutZSg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 43%

---

# Adobe Experience Platform Edge Network APIを使用したAdobe Analyticsの実装

通常、Experience Platform Edge Network APIを使用して、クライアントサイドではなくサーバーサイドでデータを収集し、IoT デバイス、セットトップボックス、デスクトップアプリケーションなどのデバイスからデータを収集します。 そして、そのデータをEdgeのネットワークやAdobe Analyticsのようなサービスに送ります。

また、機密データの収集とネットワーク全体での認証が必要な場合は、Edge Network APIを検討してください。 詳しくは、[認証](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html)を参照してください。

実装タスクの大まかな概要：

![Analytics 拡張機能ワークフローを使用した Adobe Analytics](../../assets/edge-network-server-api-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td>
<td><b>レポートスイートを定義</b>したことを確認します。</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td>
<td><b> スキーマの設定</b>。 Adobe Experience Platform を活用するアプリケーション間で使用するデータ収集を標準化するために、アドビはオープンで公的に文書化された標準であるエクスペリエンスデータモデル（XDM）を作成しました。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja">スキーマ UIの概要</a></td>
</tr>

<tr>
<td>3</td>
<td><b>データストリームを設定します</b>。 データストリームは、Adobe Experience Platform Edge Network APIからAPIを使用する場合のサーバーサイド設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja">データストリームの設定<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>単一イベントデータとバッチイベントデータ収集APIを使用して、データ収集を実装し、テストします</b>。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja">単一イベントデータ収集</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html"> バッチイベントデータ収集</a>
</tr>

<td>5</td>
<td>データストリームに <b>Adobe Analytics サービスを追加します</b>。 このサービスは、Adobe Analytics にデータを送信するかどうかと、どのように送信するかを制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=ja">Adobe Analytics の操作</a></td>
</tr>


</table>

詳しくは、[Edge Network API ドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=ja)を参照してください。

