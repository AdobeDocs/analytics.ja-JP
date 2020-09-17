---
title: 開発実装の検証と実稼動環境への公開
description: Adobe Experience Platform Launchを使用して実稼働環境にAdobe Analyticsを導入する方法を学びます。
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 93%

---


# 開発実装の検証と実稼動環境への公開

Adobe Experience Platform Launch ライブラリが実稼動環境にプッシュされると、組織は Adobe Analytics を使用して基本的なレポートの取り込みを開始できます。

## 前提条件

[Analytics 実装を開発環境にデプロイする](deploy-dev.md)：このページの手順をおこなうには、Analytics 実装を開発環境に公開する必要があります。

## Experience Cloud デバッガーを使用した開発環境の実装の検証

Experience Cloud デバッガーは、ページに存在するすべての Experience Cloud タグを表示する Chrome プラグインです。

1. [Chrome Web ブラウザー](https://www.google.com/intl/ja/chrome/)を開き、Chrome Web ストアで [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) に移動して拡張機能をインストールします。
2. Launch を実装した開発用 Web サイトに移動します。
3. Chrome の右上にある Adobe Experience Cloud デバッガーアイコンをクリックします。
4. すべてが正しく実装されている場合は、Adobe Analytics、Adobe Experience Platform Launch および Adobe Experience Cloud 訪問者 ID サービス内に次のコンテンツが表示されます。

![debugger][assets/debugger.png]

## ステージング／実稼動環境に開発環境の実装をデプロイする

データを確認したら、実装を本番用サイトにプッシュできます。

1. [Adobe Experience Platform Launch](https://launch.adobe.com) に移動して、要求された場合はログインします。
2. サイトに実装する Launch プロパティをクリックします。
3. 「公開」タブをクリックし、開発列でライブラリを探します。
4. ライブラリのドロップダウンをクリックし、「承認用に送信」を選択します。モーダルウィンドウで「送信」をクリックします。
5. ライブラリのドロップダウン（「送信済み」列に表示）を再度クリックし、「ステージング用にビルド」を選択します。
6. しばらくすると、ライブラリの黄色のライトが緑色に変わり、ビルドが正常に完了したことを示します。
7. ライブラリのドロップダウンを再度クリックし、「公開の承認」を選択します。
8. ライブラリのドロップダウン（「承認済み」列に表示）を再度クリックし、「実稼動用にビルドおよび公開」を選択します。
9. 「環境」タブに移動し、「実稼動環境」をクリックします。
10. 実稼動用のヘッダーとフッターのコードをコピーし、Web サイトの所有者に提供します。サイトの実稼動環境にこのコードを実装するように要求します。

## 実稼動環境の実装を検証します。

本番用サイトのデータが表示されていることを確認し、Adobe Analytics の正式なデータ収集を開始します。

1. Web サイトの所有者が Launch コードを実稼動にプッシュしたことを確認したら、Chrome で Web サイトのホームページに移動し、Adobe Experience Cloud デバッガーを開きます。
2. すべてが機能している場合は、開発環境でのテストと類似したデータが表示されます。この時点で、サイト上のデータを収集するようになっており、レポートへの Adobe Analytics の使用を開始できます。

## トラブルシューティング

**デバッガーにデータが表示されません。**

サイトにアクセスしている間に、ブラウザーのデベロッパーコンソール（通常は F12）を開きます。ページのソースコードを見て、次の条件が満たされていることを確認します。

* コンソールに JavaScript エラーはありません。組織の Web サイトの所有者と協力して、すべての JS エラーが解決されていることを確認します。
* ヘッダーコードが正しく実装されている：ヘッダーコードが `<head>` タグ内にあり、ファイルが存在することを確認してください。
* AppMeasurement ライブラリが存在します：JS ソースに直接移動し、JS ファイルにコードが含まれていることを確認します。表示されない場合は、各環境が作成され、それぞれの環境にライブラリが公開されていることを確認します。
* 干渉プラグイン：一部の Chrome プラグインは、画像リクエストの発動を防ぐことがあります。アドビのサーバーへのデータの送信を停止する可能性のあるプラグインを無効にします。

## 次の手順

基本的な実装が設定されたので、組織内の役割が、どのパスに関して詳しく知りたいかに影響を与えることができます。

* [ソリューションデザインドキュメントの作成](../prepare/solution-design.md)：カスタム変数の使用方法を計画し、実装に含めます。
* [Analysis Workspace の使用を開始する](/help/analyze/analysis-workspace/home.md)：ツールの主力機能を使用して、Adobe Analytics に直接アクセスします。
