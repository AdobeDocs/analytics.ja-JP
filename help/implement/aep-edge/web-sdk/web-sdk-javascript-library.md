---
title: Web SDK JavaScript ライブラリを使用したAdobe Analyticsへのデータの送信
description: まず、JavaScript ライブラリを使用してAdobe Analyticsにデータを送信する、クリーンな Web SDK の実装から始めます。
exl-id: 593b63ac-e411-4f88-af7e-78f026269ec0
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 18%

---

# Web SDK JavaScript ライブラリを使用したAdobe Analyticsへのデータの送信

この実装パスには、Web SDK JavaScript ライブラリを使用した新規 Web SDK インストールが含まれます。 その他の実装パスについては、次の別のページで説明しています。

* [Web SDK タグ拡張機能 ](web-sdk-tag-extension.md):Web SDK タグ拡張機能を使用した新規 Web SDK インストール。 Web SDK JavaScript ライブラリアプローチ（このページ）と似ていますが、Adobe Experience Platform Data Collection のタグを使用して実装を管理する点が異なります。 これには、XDM スキーマに含める一般的な Analytics 変数を含むAdobe Analytics ExperienceEvent フィールドグループが必要です。
* [Analytics 拡張機能を Web SDK 拡張機能に ](analytics-extension-to-web-sdk.md):Adobe Analytics タグ拡張機能から Web SDK タグ拡張機能にスムーズかつ系統的なアプローチで移行します。 このアプローチにより、Customer Journey AnalyticsなどのAdobe Experience Platform サービスを使用する準備が整うまで XDM を使用する必要がなくなります。 データをAdobeに送信するには、`xdm` オブジェクトではなく `data` オブジェクトを使用します。
* [Web SDK JavaScript ライブラリへのAppMeasurement](appmeasurement-to-web-sdk.md): タグを使用しない点を除き、Web SDK に移行するためのスムーズで系統的なアプローチです。 代わりに、Adobe Analytics データ収集ライブラリ（`AppMeasurement.js`）を手動で削除し、Web SDK JavaScript ライブラリ（`alloy.js`）に置き換えることができます。

## この実装パスのメリットとデメリット

Web SDK JavaScript ライブラリを使用してAdobe Analyticsにデータを送信する場合、メリットとデメリットの両方があります。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**直接のアプローチ**：この実装パスは、既存のAdobe Analytics実装を移行するアプローチよりも簡単です。 現在Adobe Analyticsの実装を心配する必要がない場合は、該当する Web SDK XDM フィールドに値を入力します。</li><li>**定義済みのスキーマ**：独自のスキーマが必要ない場合は、Adobe Analytics向けのスキーマを使用するだけです。 この概念は、Customer Journey Analyticsに向かう途中でも当てはまります。prop と eVar の概念はCustomer Journey Analyticsには当てはまりませんが、prop と eVar を単純なカスタムディメンションとして引き続き使用できます。</li></ul> | <ul><li>**実装の変更には開発者の介入が必要**:Web SDK の実装を変更する場合は、開発チームと協力してサイトのコードを編集する必要があります。 [Web SDK タグ拡張機能 ](web-sdk-tag-extension.md) を使用するアプローチでは、この欠点を回避できます。</li><li>**特定のスキーマを使用してにロック**：組織がCustomer Journey Analyticsに移行する場合、Adobe Analytics スキーマを引き続き使用するか、独自の組織のスキーマ（個別のデータセット）に移行するかを選択する必要があります。 Customer Journey Analyticsへの移行時にAdobe Analytics スキーマと個別のデータセットへの移行の両方を避けたい場合、Adobeでは次の 2 つの方法のいずれかを推奨します。</li><ul><li>`data` オブジェクトの使用：`data` オブジェクトを使用すると、XDM スキーマに準拠せずにAdobe Analyticsにデータを送信できます。 組織のスキーマが作成されたら、データストリームマッピングを使用して、`data` のオブジェクトフィールドを XDM にマッピングできます。 [Analytics extension to Web SDK extension](analytics-extension-to-web-sdk.md) と [Extension to Web SDK JavaScriptの両方のAppMeasurementで ](appmeasurement-to-web-sdk.md) この `data` オブジェクトを使用します。</li><li>Adobe Analyticsを完全にスキップする：Web SDK を実装している場合は、そのデータをAdobe Experience Platformのデータセットに送信して、Customer Journey Analyticsで使用できます。 任意のスキーマを使用できます。Adobe Analyticsは、このワークフローにはまったく関与しないので、Adobe Analytics ExperienceEvent フィールドグループは必要ありません。 この方法では、最低限の技術的負債しか発生しませんが、Adobe Analyticsは完全に全体像から外れています。</li></ul></ul> |

>[!IMPORTANT]
>
>この実装方法では、Adobe Analytics用に設定されたスキーマを使用する必要があります。 今後、組織がCustomer Journey Analyticsで独自のスキーマを使用する予定がある場合、Adobe Analytics スキーマを使用すると、データ管理者やアーキテクトの混乱を招く可能性があります。 この障害を軽減するには、いくつかの選択肢があります。
>
>* CJA では、Adobe Analytics スキーマを使用できます。 CJA には prop や eVar の概念がなく、他のスキーマフィールドとして扱われます。 また、CJA でAdobe Analytics スキーマを使用すると、Adobe Journey OptimizerやReal-time Customer Data Platformなどの他のプラットフォームサービスを使用するのが難しくなる場合があります。
>* 移行ワークフローと同様に、データオブジェクトを使用できます。 なお、データオブジェクトを使用するには、各データオブジェクトフィールドを XDM スキーマフィールドにマッピングする必要があります。
>* Adobe Analyticsの実装を完全にスキップし、独自のスキーマを使用してAdobe Experience Platformにデータを送信できます。 このアプローチは理想的な長期的アプローチで、組織がCustomer Journey Analyticsを使い始めることができます。

## Web SDK JavaScript ライブラリを実装するために必要な手順

実装タスクの大まかな概要：

![ この節で説明しているように、Web SDK ワークフローを使用してAdobe Analyticsを実装する方法 ](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>タスク</b></th><th style="width:35%"><b>詳細情報</b></th>
</tr>

<tr>
<td>1</td>
<td><b>レポートスイートを定義</b>したことを確認します。</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">レポートスイートマネージャー</a></td>
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
<td> 4</td>
<td><b>事前ビルドスタンドアロンバージョンをインストールします</b>。CDN のライブラリ（<code>alloy.js</code>）をページで直接参照するか、ダウンロードして独自のインフラストラクチャにホストすることができます。または、NPM パッケージを使用することもできます。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html?lang=ja">事前ビルドスタンドアロンバージョンのインストール</a>および<a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html?lang=ja">NPM パッケージの使用</a></td>
</tr>

<tr>
<td>5</td>
<td><b>データストリームを設定</b>します。データストリームは、Adobe Experience Platform Web SDK を実装する際のサーバーサイド設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja">データストリームの設定<a></td> 
</tr>

<td>6</td>
<td>データストリームに <b>Adobe Analytics サービス</b>を追加します。このサービスは、データをAdobe Analyticsに送信するかどうかと、どのように送信するか、および具体的にどのレポートスイートに送信するかを制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja#analytics">データストリームへの Adobe Analytics サービスの追加</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Web SDK を設定</b>します。手順 4 でインストールしたライブラリが、データストリーム ID （以前のエッジ設定 ID （<code>datastreamId</code>））、組織 ID （<code>orgId</code>）、その他の使用可能なオプションで適切に設定されていることを確認します。 変数が適切にマッピングされていることを確認します。 </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html?lang=ja">Web SDK</a><br/><a href="../xdm-var-mapping.md">XDM オブジェクト変数マッピングの設定 </a></td>
</tr>

<tr>
<td>8</td>
<td><b>コマンドを実行</b>したり、<b>イベントを追跡</b>したりします。Web ページにベースコードが実装されたら、SDK を使用してコマンドの実行とイベントの追跡を開始できます。
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/sendevent/overview.html?lang=ja">イベントの送信</a></td>
</tr>

<tr>
<td>9</td><td>実装を実稼動環境にプッシュする前に、<b>実装を拡張して検証します</b>。</td><td></td> 
</tr>
</table>
