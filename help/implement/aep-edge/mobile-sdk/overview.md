---
title: Adobe Experience Platform Mobile SDK を使用した Adobe Analytics の実装
description: Adobe Experience Platform データ収集の Mobile SDK 拡張機能を使用して、Adobe Analytics にデータを送信します。
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
feature: Implementation Basics
source-git-commit: d9948fbb63d44c851e08745c77af5618de84a89c
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 100%

---

# Adobe Experience Platform Mobile SDK を使用した Adobe Analytics の実装

Adobe Experience Platform Mobile SDK は、モバイルアプリでの Adobe Experience Cloud のソリューションとサービスを強化するのに役立ちます。Android™、iOS および様々なクロスプラットフォーム開発フレームワークで使用できます。設定は、Adobe Experience Platform データ収集を通じて処理されます。

>[!IMPORTANT]
>
>Adobe Analytics 拡張機能は、Adobe Experience Platform データ収集でも使用できます。この拡張機能をインストールする場合、XDM や Edge ネットワークを利用することはできません。

## Adobe Experience Platform SDK

実装タスクの大まかな概要：

![Analytics 拡張機能ワークフローを使用した Adobe Analytics](../../assets/mobilesdk-annotated.png)

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
<td><b>データストリームを設定します</b>。 データストリームは、Adobe Experience Platform Web SDK を実装する際のサーバーサイド設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja">データストリームの設定<a></td> 
</tr>

<td>4</td>
<td>データストリームに <b>Adobe Analytics サービスを追加します</b>。このサービスは、Adobe Analytics にデータを送信するかどうかと、どのように送信するかを制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja#analytics">データストリームへの Adobe Analytics サービスの追加</a></td>
</tr>

<tr>
<td>5</td>
<td><b>モバイルプロパティを作成します</b>。プロパティは、拡張機能、ルール、データ要素およびライブラリを入れるコンテナです。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">モバイルプロパティの設定</a></tr>

<tr>
<td>6</td>
<td>モバイルタグプロパティに <b>Adobe Experience Platform Edge Network 拡張機能をインストール</b>し、拡張機能でデータストリームを設定します。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>7</td>
<td><b>アプリでコードを使用</b>して、必要な拡張機能を登録し、タグ設定を読み込みます。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">設定の指定</a></td>
</tr>

<tr>
<td>8</td>
<td>アプリでのタグのデータ要素、ルール、追加の拡張機能、SDK API 呼び出しの組み合わせを使用して、<b>機能を実装およびテストします</b>。モバイルアプリケーションのデータ収集とエクスペリエンスを検査、検証およびデバッグします。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">サンプルアプリケーションの使用</a>
</tr>

<tr>
<td>9</td>
<td>実稼動環境にプッシュする前に、<b>モバイルアプリの実装を拡張して検証します</b>。</td>
<td></td> 
</tr>

</table>


## Adobe Analytics 拡張機能.

実装タスクの大まかな概要：

![Analytics 拡張機能ワークフローを使用した Adobe Analytics](../../assets/mobilesdk-analytics-annotated.png)

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
<td>モバイルタグプロパティに <b>Adobe Analytics 拡張機能をインストール</b>し、拡張機能がレポートスイートを指すように設定します。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">モバイルプロパティ用 Adobe Analytics 拡張機能</a>
</tr>

<tr>
<td>4</td>
<td><b>アプリでコードを使用</b>して、必要な拡張機能を登録し、タグ設定を読み込みます。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">設定の指定</a></td>
</tr>

<tr>
<td>5</td>
<td>アプリでのタグのデータ要素、ルール、追加の拡張機能、SDK API 呼び出しの組み合わせを使用して、<b>機能を実装およびテストします</b>。モバイルアプリケーションのデータ収集とエクスペリエンスを検査、検証およびデバッグします。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">サンプルアプリケーションの使用</a>
</tr>

<tr>
<td>6</td>
<td>実稼動環境にプッシュする前に、<b>モバイルアプリの実装を拡張して検証します</b>。</td>
<td></td> 
</tr>

</table>

## その他のリソース

- [タグのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)

- [Mobile SDK ドキュメント](https://developer.adobe.com/client-sdks/documentation/)
