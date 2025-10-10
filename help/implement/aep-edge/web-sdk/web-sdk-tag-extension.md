---
title: Web SDK タグ拡張機能を使用したAdobe Analyticsへのデータの送信
description: まず、XDM とAdobe Analytics ExperienceEvent フィールドグループを使用してAdobe Experience Platform データ収集からAdobe Analyticsにデータを送信する、クリーンなデータ収集の実装から始めます。
exl-id: 235b3d68-92dd-4ca4-8889-1e1f2d83f47e
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 16%

---

# Web SDK タグ拡張機能を使用したAdobe Analyticsへのデータの送信

この実装パスには、Adobe Experience Platform Data Collection のタグを使用した新しい web SDKのインストールが含まれます。 その他の実装パスについては、次の別のページで説明しています。

* [Web SDK JavaScript ライブラリ ](web-sdk-javascript-library.md):Web SDK JavaScript ライブラリ（`alloy.js`）を使用した新規の Web SDK インストール。 Web SDKのタグ拡張機能のアプローチ（このページ）と似ていますが、タグ UI を使用する代わりに自分で実装を管理する点が異なります。 これには、XDM スキーマに含める一般的な Analytics 変数を含むAdobe Analytics ExperienceEvent フィールドグループが必要です。
* [Analytics 拡張機能を web SDK拡張機能に ](analytics-extension-to-web-sdk.md):Adobe Analytics タグ拡張機能から Web SDK タグ拡張機能にスムーズかつ系統的なアプローチで移行します。 このアプローチにより、Customer Journey AnalyticsなどのAdobe Experience Platform サービスを使用する準備が整うまで XDM を使用する必要がなくなります。 データをAdobeに送信するには、`data` オブジェクトの代わりに `xdm` オブジェクトを使用します。
* [AppMeasurementから Web SDK JavaScript ライブラリへ ](appmeasurement-to-web-sdk.md): タグを使用しない点を除き、Web SDKへの移行をスムーズかつ計画的に行います。 代わりに、手動でAdobe Analytics データ収集ライブラリ（`AppMeasurement.js`）を削除し、web SDK JavaScript ライブラリ（`alloy.js`）に置き換えます。

## この実装パスのメリットとデメリット

Web SDK拡張機能を使用してAdobe Analyticsにデータを送信する場合、メリットとデメリットの両方があります。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**最も直接的なアプローチ**：この実装パスは最も簡単で、通常は新しい web SDK実装に推奨されるパスです。 現在Adobe Analyticsの実装を心配する必要がない場合は、該当する Web SDK XDM フィールドに値を入力します。</li><li>**定義済みのスキーマ**：独自のスキーマが必要ない場合は、Adobe Analytics向けのスキーマを使用するだけです。 この概念は、Customer Journey Analyticsに向かう場合でも当てはまります。prop と eVar の概念はCustomer Journey Analyticsには当てはまりませんが、prop と eVar を単純なカスタムディメンションとして引き続き使用できます。</li><li>**開発者の操作なしでタグを管理**：タグを使用すると、開発者に実装のコード変更をリクエストせずに実装を管理できます。 開発者がタグローダースクリプトをインストールすると、データの収集方法を完全に制御できます。</li></ul> | <ul><li>**特定のスキーマを使用してにロック**：組織がCustomer Journey Analyticsに移行する場合、Adobe Analyticsのスキーマを引き続き使用するか、独自の組織のスキーマ（個別のデータセット）に移行するかを選択する必要があります。 Customer Journey Analyticsへの移行時にAdobe Analytics スキーマと個別のデータセットへの移行の両方を避けたい場合、Adobeでは次の 2 つの方法のいずれかを使用することをお勧めします。<ul><li>`data` オブジェクトの使用：`data` オブジェクトを使用すると、XDM スキーマに準拠せずにAdobe Analyticsにデータを送信できます。 組織のスキーマが作成されたら、データストリームマッピングを使用して、`data` のオブジェクトフィールドを XDM にマッピングできます。 [Analytics 拡張機能から Web SDK拡張機能 ](analytics-extension-to-web-sdk.md) および [AppMeasurementから Web SDK JavaScript ライブラリ ](appmeasurement-to-web-sdk.md) の両方がこの `data` オブジェクトを使用します。</li><li>Adobe Analyticsを完全にスキップする：Web SDKを実装している場合は、そのデータをAdobe Experience Platformのデータセットに送信して、Customer Journey Analyticsで使用できます。 任意のスキーマを使用できます。Adobe Analyticsは、このワークフローにはまったく関与しないので、Adobe Analytics ExperienceEvent フィールドグループは必要ありません。 この方法では、最低限の技術的負債しか発生しませんが、Adobe Analyticsは完全に全体像から外れています。</li></ul></ul> |

>[!IMPORTANT]
>
>この実装方法では、Adobe Analytics用に設定されたスキーマを使用する必要があります。 今後、組織がCustomer Journey Analyticsで独自のスキーマを使用する予定がある場合、Adobe Analytics スキーマを使用すると、データ管理者やアーキテクトの混乱を招く可能性があります。 この障害を軽減するには、いくつかの選択肢があります。
>
>* CJAでAdobe Analytics スキーマを使用できます。 CJAには prop や eVar の概念がなく、他のスキーマフィールドとして扱われます。 また、CJAでAdobe Analytics スキーマを使用すると、Adobe Journey OptimizerやReal-Time Customer Data Platformなどの他の Platform サービスを使用するのが難しくなる可能性があります。
>* 移行ワークフローと同様に、データオブジェクトを使用できます。 なお、データオブジェクトを使用するには、各データオブジェクトフィールドを XDM スキーマフィールドにマッピングする必要があります。
>* Adobe Analyticsの実装を完全にスキップし、独自のスキーマを使用してAdobe Experience Platformにデータを送信できます。 このアプローチは理想的な長期的アプローチで、組織がCustomer Journey Analyticsを使い始めることができます。

## Web SDK タグ拡張機能を実装するために必要な手順

実装タスクの大まかな概要：

![ この節で説明しているように、Web SDK拡張機能ワークフローを使用してAdobe Analyticsを実装する方法 ](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td>
<td><b>レポートスイートを定義</b>したことを確認します。</td>
<td><a href="/help/admin/tools/manage-rs/report-suites-admin.md">レポートスイートマネージャー</a></td>
</tr>

<tr>
<td>2</td>
<td><b> スキーマを設定 </b>. Adobe Experience Platform を活用するアプリケーション間で使用するデータ収集を標準化するために、アドビはオープンで公的に文書化された標準である Experience Data Model（XDM）を作成しました。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=ja">スキーマ UI の概要</a></td>
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
<td>データストリームに <b>Adobe Analytics サービスを追加します</b>。 このサービスは、データをAdobe Analyticsに送信するかどうかと、どのように送信するか、および具体的にどのレポートスイートに送信するかを制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">データストリームへの Adobe Analytics サービスの追加</a></td>
</tr>

<tr>
<td>6</td>
<td><b> タグプロパティの作成 </b>。 プロパティは、タグ管理データを参照するために使用される包括的なコンテナです。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html#for-web">Web 用のタグプロパティの作成または設定</a></td>
</tr>

<tr>
<td>7</td> 
<td>タグプロパティに <b>Web SDK 拡張機能をインストールして設定します</b>。手順 4 で設定したデータストリームにデータを送信するように Web SDK 拡張機能を設定します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=ja">Adobe Experience Platform Web SDK 拡張機能の概要</a></td>
</tr>

<tr>
<td>8</td>
<td><b>反復し、検証して実稼動環境に公開します</b>。タグプロパティを web サイトページに含めるためのコードを埋め込みます。 次に、データ要素、ルールなどを使用して、実装をカスタマイズします。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html#embed-code"> 埋め込みコード </a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=ja"> 公開の概要 </a></td>
</tr>

</table>
