---
title: Launch での Analytics プロパティの作成
description: Adobe Experience Platform Launch を使用してスペースを作成し、データの収集方法をカスタマイズします。
translation-type: ht
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Adobe Experience Platform Launch での Analytics プロパティの作成

Adobe Experience Platform Launch は、Web サイト上で Experience Cloud ソリューション（Analytics を含む）を統合できるツールです。このページでは、Launch 管理者が Adobe Analytics の基本的な実装を正しく設定する方法について詳しく説明します。

## 前提条件

[レポートスイートの作成](/help/admin/admin-console/create-report-suite.md)：収集する Analytics データ用のサイロを作成します。

## プロパティを作成し、重要な拡張機能をインストールする

プロパティは、タグの管理に使用する包括的なコンテナです。拡張機能を使用すれば、製品固有のタグをインストールして設定できます。

1. [launch.adobe.com](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. 「新規プロパティ」をクリックします。
1. プロパティに Web サイトのタイトルなどの名前を付け、Analytics を実装するドメインを入力します。「保存」をクリックします。
1. 新しく作成したプロパティをクリックして、設定を入力します。
1. 「拡張機能」タブをクリックし、「カタログ」をクリックします。
1. 「ID サービス」を探し、「インストール」をクリックします。
1. Experience Cloud 組織 ID を含むすべての設定は、既に入力されているはずです。「保存」をクリックします。
1. エクステンションカタログに戻り、Adobe Analytics を探して「インストール」をクリックします。

## Adobe Analytics 用のデータ要素の作成

データ要素は、変数値を収集するための、サイトの特定の部分に対する参照です。

1. [launch.adobe.com](https://launch.adobe.com) に移動して、要求された場合はログインします。
2. サイトに実装する Launch プロパティをクリックします。
3. 「データ要素」タブをクリックし、「新しいデータ要素の作成」をクリックします。
4. データ要素に次の設定を指定します。
   * 名前：ページ名
   * 拡張機能：Core
   * データ要素の種類：JavaScript 変数
   * 変数へのパス：`window.document.title`
      > [!NOTE]注意：これは、使い始めるのに役立つ値の例です。データレイヤーの値など、ページ名に適した値を組織が定義する場合は、ここに入力できます。
   * クリーンテキストの確認
   * 期間：Pageview
5. 「保存」をクリックします。

## Adobe Analytics のルールの作成

ルールは、データ要素を Analytics 変数値にマッピングし、それらの値がアドビのサーバーに送信されるタイミングを決定します。

1. [launch.adobe.com](https://launch.adobe.com) に移動して、要求された場合はログインします。
1. サイトに実装する Launch プロパティをクリックします。
1. 「新しいルールを作成」をクリックし、`Global Rule` と名前を付けます。
1. イベントの横にある「追加」をクリックし、次の設定を入力します。
   * 拡張機能：Core
   * イベントタイプ：読み込まれたライブラリ（ページ上部）
   * 名前：Core - 読み込まれたライブラリ（ページ上部）
   * 注文：50
1. 「変更を保持」をクリックします。
1. 「アクション」で、「追加」をクリックし、次の設定を入力します。
   * 拡張機能：Adobe Analytics
   * アクションタイプ：変数を設定
   * ページ名：コンテナアイコンをクリックし、`Page Name`データ要素を選択します
   * キャンペーン：値が `cid` のクエリーパラメーター
1. 「変更を保持」をクリックします。
1. アクションの横のプラス記号をクリックして別のアクションを追加し、次の設定を入力します。
   * 拡張機能：Adobe Analytics
   * アクションタイプ：ビーコンを送信
   * 名前：Adobe Analytics - ビーコンを送信
   * トラッキング：s.t()
1. 「変更を保持」をクリックします。
1. イベントと 2 つのアクションが設定されていることを確認し、「保存」をクリックします。

## ドキュメントとその他のリソース

* [Adobe Analytics 拡張機能のドキュメント](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension)： Adobe Experience Platform Launch の Adobe Analytics 拡張機能に固有の完全なドキュメントです。
* [Launch 使用の手引き](https://docs.adobelaunch.com/getting-started)：より詳細なスタートガイドを含む、Launch の完全なドキュメントです。
* [Adobe Experience Platform Launch YouTube チャンネル](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&amp;shelf_id=0&amp;sort=dd)：ビデオを通して Launch の使用方法を学びます。

## 次の手順

[Analytics 実装を開発環境にデプロイする](deploy-dev.md)：テスト環境で Analytics コードを使用します。
