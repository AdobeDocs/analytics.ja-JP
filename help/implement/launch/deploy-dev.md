---
title: 開発環境への Adobe Analytics のデプロイ
description: Adobe Experience Platform Launch を使用して、Adobe Analytics を開発環境にデプロイする方法を説明します。
translation-type: ht
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b
workflow-type: ht
source-wordcount: '548'
ht-degree: 100%

---


# 開発環境への Analytics 実装のデプロイ

Launch でプロパティが作成および設定されると、サイト上でライブラリを展開してコードを実装する準備が整います。

## 前提条件

[Launch で Adobe Analytics 用にプロパティを作成および設定する](create-analytics-property.md)：ツールにアクセスして、Analytics 実装用のスペースを作成します。

## アダプターと環境の作成

Launch は、コードをデプロイする多くの組織的なワークフローに対応しています。Analytics の実装に最低限必要なコンポーネントを作成するには、次の手順に従います。Launch 管理者は組織内で協力して、アドビソリューションのデプロイに適したワークフローを確立できます。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
2. サイトに実装する Launch プロパティをクリックします。
3. 「アダプター」タブをクリックし、「アダプターの追加」をクリックします。
4. 「Akamai」という名前を付け、タイプドロップダウンで「Akamai」を選択します。「保存」をクリックします。
5. 「環境」タブに移動し、「新しい環境の作成」をクリックします。
6. 「開発」を選択し、「開発環境」という名前を付け、ドロップダウンから Akamai アダプターを選択します。「作成」をクリックし、「閉じる」をクリックします。
7. 「環境を追加」をクリックして「ステージング」を選択し、「ステージング環境」という名前を付け、Akamai アダプターを選択します。「作成」をクリックし、「閉じる」をクリックします。
8. もう一度「環境を追加」をクリックして「実稼動」を選択し、「実稼動環境」という名前を付け、Akamai アダプターを選択します。「作成」をクリックし、「閉じる」をクリックします。

## 開発用ライブラリの構築

ここまでにおこなったすべての変更や設定にもかかわらず、実際にはコードは公開されていません。ライブラリ（変更の集まりのようなもの）を作成すれば、サイトで使用するコードを公開できます。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
2. サイトに実装する Launch プロパティをクリックします。
3. 「公開」タブをクリックし、「新しいライブラリの追加」をクリックします。
4. ライブラリに「初期変更」という名前を付け、開発環境を選択します。
5. 「変更されたすべてのリソースを追加」をクリックすると、Adobe Analytics、ID サービスおよび Core が自動的に表示されます。
6. 「保存」をクリックします。
7. 投稿ワークフロー画面に戻り、新しいライブラリの横にあるドロップダウンをクリックし、「開発用にビルド」をクリックします。数秒後、ライブラリの黄色い丸が緑色に変わり、ビルドが成功したことを示します。
8. 「環境」タブに移動し、開発環境をクリックします。
9. 「Launch をインストール」の下で、コードブロックをコピーし、組織の Web サイト所有者に提供します。

## Web サイトの開発環境に Launch をインストールする

Web サイトのコードを制御する場合は、サイトの各ページのそれぞれの場所（`<head>` タグ内および終了 `</body>` タグのすぐ上）に、2 つのコードブロックを実装します。このコードは、通常、サイトのオーバーチャーチテンプレートに配置されます。実装コードのみを含む空白のページは、次のようになります。

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## トラブルシューティング

**ビルドに失敗しました。**

一般的な理由として、ステージングまたは実稼動環境にプッシュされた他のライブラリに要素が既に存在しているというものがあります。ライブラリを最初に作成する場合は、変更後のリソースのみがライブラリに追加されていることを確認します。

## ドキュメントとその他のリソース

- [はじめに](https://docs.adobe.com/content/help/ja-JP/launch/using/intro/get-started/quick-start.html)：Launch の基本を学習します。
- [Launch の公開](https://docs.adobe.com/content/help/ja-JP/launch/using/reference/publish/overview.html)：公開と環境についての詳細。

## 次の手順

[Analytics の実装を検証し、実稼動環境に公開する](validate-publish-prod.md)：Adobe Analytics の価値の活用を開始します。
