---
title: 開発環境へのAdobe Analyticsのデプロイ
seo-title: 開発環境へのAdobe Analyticsのデプロイ
description: Adobe Experience Platform Launchを使用してAdobe Analyticsを開発環境にデプロイする方法について説明します。
seo-description: Adobe Experience Platform Launchを使用してAdobe Analyticsを開発環境にデプロイする方法について説明します。
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 開発環境へのAnalytics実装のデプロイ

起動時にプロパティを作成して設定すると、ライブラリをデプロイしてサイトにコードを実装できます。

## 前提条件

[起動時に、Adobe Analyticsのプロパティを作成し、設定](create-analytics-property.md)します。ツールにアクセスし、Analytics実装用のスペースを作成します。

## アダプターと環境の作成

起動はコードの導入に多くの組織ワークフローに対応しています。Analytics実装の必要最小限のコンポーネントを作成するには、次の手順に従います。開始管理者として、組織内で作業を行って、アドビソリューションの導入に適したワークフローを確立できます。

1. [Adobe Experience Platform Launchに移動](https://launch.adobe.com) し、プロンプトが表示されたらログインします。
2. サイトに実装する起動プロパティをクリックします。
3. 「アダプター」タブをクリックし、「アダプターを追加」をクリックします。
4. "Akamai"という名前を付け、タイプドロップダウンリストで"Akamai"を選択します。「保存」をクリックします。
5. 「環境」タブに移動し、「新規環境を作成」をクリックします。
6. 「開発」を選択し、「開発環境」という名前を付けて、ドロップダウンからAkamaiアダプターを選択します。「作成」をクリックし、「閉じる」をクリックします。
7. 「環境を追加」をクリックし、「ステージング」を選択して「ステージング環境」を選択し、Akamaiアダプターを選択します。「作成」をクリックし、「閉じる」をクリックします。
8. 「環境を追加」を再度クリックし、「本番環境」を選択して「実稼動環境」に名前を付け、Akamaiアダプターを選択します。「作成」をクリックし、「閉じる」をクリックします。

## 開発用ライブラリの作成

これまでに行われた変更や設定にもかかわらず、コードは実際には公開されていません。変更のコレクションとしてほぼ翻訳されたライブラリを作成すると、サイトで使用するコードを公開できます。

1. [Adobe Experience Platform Launchに移動](https://launch.adobe.com) し、プロンプトが表示されたらログインします。
2. サイトに実装する起動プロパティをクリックします。
3. 「公開」タブをクリックし、「新しいライブラリを追加」をクリックします。
4. ライブラリの"Initial changes"に名前を付け、開発環境を選択します。
5. 「変更されたすべてのリソースを追加」をクリックすると、Adobe Analytics、IDサービスおよびコアが自動的に一覧表示されます。
6. 「保存」をクリックします。
7. 公開ワークフロー画面で、新しいライブラリの横にあるドロップダウンをクリックし、「開発用にビルド」をクリックします。数秒後、ライブラリの黄色のドットが緑色に変わり、ビルドが成功したことを示しています。
8. 「環境」タブに移動し、開発環境をクリックします。
9. "Launch Launch"の下で、コードブロックをコピーして、組織のWebサイト所有者に提供します。

## Webサイトの開発環境への起動のインストール

If you control your website's code, implement the two blocks of code in their respective locations (in the `<head>` tag and just above the closing `</body>` tag) on every page of your site. このコードは、一般的にサイトの概要テンプレートに配置されます。実装コードを含む空白ページは、次のようになります。

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

**ビルドを試行すると、失敗します。**

一般的な理由は、ステージングまたは実稼動にプッシュされた他のライブラリに要素が既に存在するためです。ライブラリの作成時に、変更されたリソースのみをライブラリに追加するようにします。

## ドキュメントおよびその他のリソース

- [Launch使用の手引き](https://docs.adobelaunch.com/getting-started):起動の基本的なワークフローについて説明します
- [管理の起動](https://docs.adobelaunch.com/administration):アダプターと環境についての詳細情報

## 次の手順

[Analytics実装を検証し、本番](validate-publish-prod.md)環境に公開します。Adobe Analyticsから値を取得し始めます。
