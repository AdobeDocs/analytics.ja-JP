---
title: Adobe Experience Platform Mobile SDK を使用した Adobe Analytics の実装
description: Adobe Experience Platform データ収集の Mobile SDK 拡張機能を使用して、Adobe Analytics にデータを送信します。
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 30%

---

# Adobe Experience Platform Mobile SDK を使用した Adobe Analytics の実装

Adobe Experience Platform Mobile SDK は、モバイルアプリでの Adobe Experience Cloud のソリューションとサービスを強化するのに役立ちます。Android™、iOS、および様々なクロスプラットフォーム開発フレームワークで使用できます。 設定は、Adobe Experience Platform データ収集を通じて処理されます。
>[!IMPORTANT]
>
>Adobe Analytics 拡張機能は、Adobe Experience Platform データ収集でも使用できます。この拡張機能をインストールする場合、XDM や Edge ネットワークを利用することはできません。

## Adobe Experience Platform SDK

実装タスクの概要です。

![Analytics 拡張機能ワークフローを使用したAdobe Analytics](../../assets/mobilesdk-annotated.png)

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
<td><b>データストリームの設定</b>. datastream は、Adobe Experience Platform Web SDK を実装する際のサーバー側の設定を表します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">データストリームの設定<a></td> 
</tr>

<td>4</td>
<td><b>Adobe Analyticsサービスの追加</b> をデータストリームに追加します。 このサービスは、データをAdobe Analyticsに送信するかどうかと方法を制御します。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Adobe Analyticsサービスをデータストリームに追加する</a></td>
</tr>

<tr>
<td>5</td>
<td><b>モバイルプロパティの作成</b>. プロパティは、拡張機能、ルール、データ要素およびライブラリを入力するコンテナです。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">モバイルプロパティの設定</a></tr>

<tr>
<td>6</td>
<td><b>Adobe Experience Platform Edge Network 拡張機能のインストール</b> モバイルタグのプロパティを開き、拡張機能で datastream を設定します。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>7</td>
<td><b>アプリでのコードの使用</b> 必要な拡張機能を登録し、タグ設定を読み込む。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">設定のセットアップ</a></td>
</tr>

<tr>
<td>8</td>
<td><b>機能の実装とテスト</b> アプリ内でタグのデータ要素、ルール、追加の拡張機能、SDK API 呼び出しの組み合わせを使用する。 モバイルアプリケーションのデータ収集およびエクスペリエンスのInspect、検証およびデバッグをおこないます。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">サンプルアプリケーションの使用</a>
</tr>

<tr>
<td>9</td>
<td><b>モバイルアプリの実装を拡張および検証します</b> 実稼動環境にプッシュする前に</td>
<td></td> 
</tr>

</table>


## Adobe Analytics 拡張機能.

実装タスクの概要です。

![Analytics 拡張機能ワークフローを使用したAdobe Analytics](../../assets/mobilesdk-analytics-annotated.png)

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
<td><b>Adobe Analytics拡張機能のインストール</b> モバイルタグプロパティで、拡張機能を設定して、レポートスイートを指すようにします。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">モバイルプロパティ用Adobe Analytics拡張機能</a>
</tr>

<tr>
<td>4</td>
<td><b>アプリでのコードの使用</b> 必要な拡張機能を登録し、タグ設定を読み込む。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">設定のセットアップ</a></td>
</tr>

<tr>
<td>5</td>
<td><b>機能の実装とテスト</b> アプリ内でタグのデータ要素、ルール、追加の拡張機能、SDK API 呼び出しの組み合わせを使用する。 モバイルアプリケーションのデータ収集およびエクスペリエンスのInspect、検証およびデバッグをおこないます。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">サンプルアプリケーションの使用</a>
</tr>

<tr>
<td>6</td>
<td><b>モバイルアプリの実装を拡張および検証します</b> 実稼動環境にプッシュする前に</td>
<td></td> 
</tr>

</table>

## その他のリソース

- [タグドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja#)

- [Mobile SDK ドキュメント](https://developer.adobe.com/client-sdks/documentation/)



