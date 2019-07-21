---
title: 開発環境へのAdobe Analyticsのデプロイ
seo-title: 開発環境へのAdobe Analyticsのデプロイ
description: Adobe Experience Platform Launchを使用してAdobe Analyticsを開発環境にデプロイする方法について説明します。
seo-description: Adobe Experience Platform Launchを使用してAdobe Analyticsを開発環境にデプロイする方法について説明します。
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 開発実装の検証と実稼働環境への公開

Adobe Experience Platform Launchライブラリが実稼動環境にプッシュされると、組織はAdobe Analyticsを使用して基本的なレポートを引き出すことができます。

## 前提条件

[開発環境にAnalytics実装をデプロイ](deploy-dev.md)します。このページに従うには、Analytics実装を開発環境に発行する必要があります。

## Experience Cloudデバッガーを使用した開発環境の検証

Experience Cloudデバッガーは、ページに存在するすべてのExperience Cloudタグを表示するChromeプラグインです。

1. [Chrome Web Browser](https://www.google.com/chrome/) を開き、Chrome Web Storeで [Adobe Experience Cloudデバッガー](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) に移動して拡張機能をインストールします。
2. 起動した開発Webサイトに移動します。
3. Chromeの右上にあるAdobe Experience Cloudデバッガーアイコンをクリックします
4. すべてが正しく実装されている場合、Adobe Analytics、Adobe Experience Platform LaunchおよびAdobe Experience Cloud訪問者IDサービス内にコンテンツが表示されます。

![デバッガー][assets/debugger.png]

## dev実装をステージング/prodにデプロイします

データを確認したら、導入をサイトの本番バージョンにプッシュできます。

1. [Adobe Experience Platform Launchに移動](https://launch.adobe.com) し、プロンプトが表示されたらログインします。
2. サイトに実装する起動プロパティをクリックします。
3. 「公開」タブをクリックし、開発列でライブラリを見つけます。
4. ライブラリのドロップダウンをクリックし、「承認用に送信」を選択します。モーダルウィンドウで「送信」をクリックします。
5. ライブラリのドロップダウンを再度（送信済み列で）クリックし、「ステージング用にビルド」を選択します。
6. しばらくすると、ライブラリ上の黄色の色のライトが緑色に変わり、ビルドが成功したことを示します。
7. ライブラリのドロップダウンを再度クリックし、「公開用に承認」を選択します。
8. ライブラリのドロップダウンを再度（「承認済み」列で）クリックし、「ビルド」と「実稼動環境へ発行」を選択します。
9. 「環境」タブに移動し、「実稼動環境」をクリックします。
10. 本番用のヘッダーコードとフッターコードをコピーして、Webサイトの所有者に提供します。このコードをサイトの実稼働環境に実装することをリクエストします。

## 実稼働環境の実装を検証する

サイトの本番バージョンにデータが表示されていることを確認し、Adobe Analyticsの公式データ収集を開始します。

1. Webサイトの所有者から、起動コードを実稼動環境にプッシュしたことを確認したら、ChromeでWebサイトのホームページに移動し、Adobe Experience Cloudデバッガーを開きます。
2. すべてが機能している場合、開発環境でテストに類似したデータが表示されます。この時点で、サイトでデータを収集し、レポートにAdobe Analyticsを使用できるようになりました。

## トラブルシューティング

**デバッガーにデータが表示されません。**

サイト上で、ブラウザーの開発者コンソールを開きます（通常はF12）。ページのソースコードを確認し、以下が満たされていることを確認します。

* コンソールにJavaScriptエラーはありません。組織のWebサイト所有者と協力して、すべてのJSエラーが解決されていることを確認してください。
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* AppMeasurementライブラリが存在します。JSファイルにコードが含まれていることを確認するために、直接JSソースに移動します。そうでない場合は、各環境が作成されていること、およびライブラリがそれぞれの環境に公開されていることを確認してください。
* 干渉プラグイン:Chromeプラグインによっては、イメージ要求が発生しないことがあります。アドビのサーバーにデータが送信されない可能性のあるプラグインを無効にします。

## 次の手順

基本的な実装が設定されると、組織内の担当者は、どのパスについてさらに知りたいかに影響を与えることがあります。

* [ソリューションデザインドキュメント](../prepare/solution-design.md)の作成:カスタム変数の使用方法の計画と、それらを導入に含める
* [Analysis Workspaceの使用を開始](../../analyze/analysis-workspace/home.md)するには:ツールのflagship機能を使用して、Adobe Analyticsをすぐに使用できます。
