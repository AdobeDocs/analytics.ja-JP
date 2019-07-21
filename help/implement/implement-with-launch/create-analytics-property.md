---
title: 起動でのAnalyticsプロパティの作成
seo-title: Adobe Experience Platform LaunchでのAdobe Analyticsプロパティの作成
description: Adobe Experience Platform Launchを使用して、データの収集方法をカスタマイズするためのスペースを作成します。
seo-description: Adobe Experience Platform Launchを使用して、Adobe Analyticsでデータの収集方法をカスタマイズするためのスペースを作成します。
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Adobe Experience Platform LaunchでのAnalyticsプロパティの作成

Adobe Experience Platform Launchは、Webサイト上（Analyticsを含む）のExperience Cloudソリューションを統合するために使用できるツールです。ここでは、起動管理者が基本的なAdobe Analytics実装を正しく設定する方法について説明します。

## 前提条件

[レポートスイート](../../admin/admin-console/create-report-suite.md)の作成:収集するAnalyticsデータのサイロの作成

## プロパティの作成と重要な拡張機能のインストール

プロパティは、タグの管理に使用する包括的なコンテナです。拡張機能を使用すると、製品固有のタグをインストールして設定できます。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. 「新規プロパティ」をクリックします。
1. プロパティにWebサイトのタイトルなどの名前を付け、Analyticsを導入するドメインを入力します。「保存」をクリックします。
1. 新しく作成したプロパティをクリックして、設定を入力します。
1. 「拡張子」タブをクリックし、「カタログ」をクリックします。
1. IDサービスを見つけて、「インストール」をクリックします。
1. Experience Cloud組織IDを含むすべての設定は、既に入力済みである必要があります。「保存」をクリックします。
1. 拡張機能カタログに戻り、Adobe Analyticsを見つけて、「インストール」をクリックします。

## Adobe Analytics用のデータ要素の作成

データ要素は、変数値を収集するためにサイトの特定の部分への参照です。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
2. サイトに実装する起動プロパティをクリックします。
3. 「データ要素」タブをクリックし、「新しいデータ要素を作成」をクリックします。
4. データ要素に次の設定を指定します。
   * 名前:ページ名
   * 拡張子:コア
   * データ要素タイプ:JavaScript変数
   * Path to variable: `window.document.title`
      > [!NOTE] 注意:これは、開始するためのサンプル値です。データレイヤーの値など、ページ名により優れた値を定義している場合は、ここに入力できます。
   * クリーンテキストのチェック
   * 期間:ページビュー
5. 「保存」をクリックします。

## Adobe Analyticsのルールの作成

ルールは、Analytics変数の値にデータ要素をマッピングし、それらの値がアドビのサーバーに送信されるタイミングを決定します。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. サイトに実装する起動プロパティをクリックします。
1. Click Create New Rule and name it `Global Rule`.
1. イベントの横にある「追加」をクリックし、次の設定を入力します。
   * 拡張子:コア
   * イベントタイプ:ロードされたライブラリ（ページ上）
   * 名前:コア-ライブラリロード済み（ページ上）
   * 順序:50
1. 「変更を保持」をクリックします。
1. 「アクション」で「追加」をクリックし、次の設定を入力します。
   * 拡張子:Adobe Analytics
   * アクションタイプ:変数の設定
   * Page Name: click the container icon, and select the `Page Name` data element.
   * Campaign: Query parameter with a value of `cid`
1. 「変更を保持」をクリックします。
1. アクションの横にあるプラス記号をクリックして、別のアクションを追加し、次の設定を入力します。
   * 拡張子:Adobe Analytics
   * アクションタイプ:ビーコンの送信
   * 名前:Adobe Analytics-ビーコンの送信
   * トラッキング:s. t（）
1. 「変更を保持」をクリックします。
1. イベントがあり、2つのアクションが設定されていることを確認し、「保存」をクリックします。

## ドキュメントおよびその他のリソース

* [Adobe Analytics拡張機能のドキュメント](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension):Adobe Experience Platform LaunchのAdobe Analytics拡張機能に固有のドキュメントです。
* [Launch使用の手引き](https://docs.adobelaunch.com/getting-started):開始ガイドを含む、起動に関する完全なドキュメント
* [Adobe Experience Platform Launch YouTubeチャンネル](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd):ビデオからの開始を使用する方法について学習します

## 次の手順

[開発環境にAnalytics実装をデプロイ](deploy-dev.md)します。テスト環境でのAnalyticsコードの取得
