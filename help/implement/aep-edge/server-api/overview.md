---
title: Adobe Experience Platform Edge Network Server API を使用したAdobe Analyticsの実装
description: Adobe Experience Platform Edge Network Server API を使用して、Adobe Analyticsにデータを送信します。
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 34%

---

# Adobe Experience Platform Edge Network Server API を使用したAdobe Analyticsの実装

通常、Experience PlatformEdge Network Server API を使用して、クライアント側ではなくサーバー側でデータを収集し、IoT デバイス、セットトップボックス、デスクトップアプリケーションなどのデバイスからデータを収集します。 次に、そのデータを Edge ネットワークやAdobe Analyticsなどのサービスに送信します。

また、機密データをネットワークを介して安全に収集し、認証する必要がある場合は、Edge Network Server API も検討します。 詳しくは、 [認証](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html) を参照してください。

実装タスクの大まかな概要：

![Analytics 拡張機能ワークフローを使用した Adobe Analytics](../../assets/edge-network-server-api-annotated.png)

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
<td><b>スキーマを設定</b>. Adobe Experience Platform を活用するアプリケーション間で使用するデータ収集を標準化するために、アドビはオープンで公的に文書化された標準である Experience Data Model（XDM）を作成しました。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja">スキーマ UI の概要</a></td>
</tr>

<tr>
<td>3</td>
<td><b>データストリームを設定します</b>。 datastream は、Adobe Experience Platform Edge Network API から API を使用する場合のサーバー側の設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja">データストリームの設定<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>データ収集の実装とテスト</b> 単一イベントデータとバッチイベントデータ収集 API の使用</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja">単一イベントのデータ収集</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html">バッチイベントのデータ収集</a>
</tr>

<td>5</td>
<td>データストリームに <b>Adobe Analytics サービスを追加します</b>。 このサービスは、Adobe Analytics にデータを送信するかどうかと、どのように送信するかを制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.htmls">Adobe Analytics の操作</a></td>
</tr>


</table>

詳しくは、 [Edge Network Server API ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=ja)、および例 [Adobe Analyticsとの統合](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=ja) を参照してください。

