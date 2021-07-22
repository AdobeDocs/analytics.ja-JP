---
title: 開発実装の検証と実稼動環境への公開
description: Adobe Experience Platformタグを使用してAdobe Analyticsを実稼動環境にデプロイする方法を説明します。
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 64%

---

# 開発実装の検証と実稼動環境への公開

タグライブラリが実稼動環境にプッシュされると、組織はAdobe Analyticsを使用して基本レポートの取り込みを開始できます。

>[!NOTE]
>Adobe Experience Platform Launchは、Experience Platformのデータ収集テクノロジーのスイートとしてリブランドされました。 その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。 用語の変更点の一覧については、次の[ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)を参照してください。

## 前提条件

[Analytics 実装を開発環境にデプロイする](deploy-dev.md)：このページの手順をおこなうには、Analytics 実装を開発環境に公開する必要があります。

## Experience Cloud デバッガーを使用した開発環境の実装の検証

Experience Cloud デバッガーは、ページに存在するすべての Experience Cloud タグを表示する Chrome プラグインです。

1. [Chrome Web ブラウザー](https://www.google.com/intl/ja/chrome/)を開き、Chrome Web ストアで [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) に移動して拡張機能をインストールします。
2. タグを実装した開発用Webサイトに移動します。
3. Chrome の右上にある Adobe Experience Cloud デバッガーアイコンをクリックします。
4. すべてが正しく実装されている場合は、Adobe Analytics、タグおよびAdobe Experience Cloud訪問者IDサービス内のコンテンツが表示されます。

![debugger][assets/debugger.png]

## ステージング／実稼動環境に開発環境の実装をデプロイする

データを確認したら、実装を本番用サイトにプッシュできます。

1. [experience.adobe.com](https://experience.adobe.com)に移動し、プロンプトが表示されたらログインします。
1. **[!UICONTROL Launch /データ収集]**&#x200B;を選択します。
1. 「**[!UICONTROL Launch /データ収集に移動]**」をクリックし、「**[!UICONTROL タグ]**」を選択します。
1. サイトに実装するタグプロパティをクリックします。
1. 「**[!UICONTROL 公開]**」タブをクリックし、開発列でライブラリを探します。
1. ライブラリのドロップダウンをクリックし、「**[!UICONTROL 承認用に送信]**」を選択します。 モーダルウィンドウで「**[!UICONTROL 送信]**」をクリックします。
1. ライブラリのドロップダウン（「送信済み」列に表示）を再度クリックし、「**[!UICONTROL ステージング用にビルド]**」を選択します。
1. しばらくすると、ライブラリの黄色のライトが緑色に変わり、ビルドが正常に完了したことを示します。
1. ライブラリのドロップダウンを再度クリックし、「**[!UICONTROL 公開の承認]**」を選択します。
1. ライブラリのドロップダウン（「[!UICONTROL 承認済み]」列に表示）を再度クリックし、「**[!UICONTROL ビルドして実稼動環境にパブリッシュ]**」を選択します。
1. 「環境」タブに移動し、「**[!UICONTROL 実稼動環境]**」をクリックします。
1. 実稼動用のヘッダーとフッターのコードをコピーし、Web サイトの所有者に提供します。サイトの実稼動環境にこのコードを実装するように要求します。

## 実稼動環境の実装を検証します。

本番用サイトのデータが表示されていることを確認し、Adobe Analytics の正式なデータ収集を開始します。

1. Webサイトの所有者がタグコードを実稼動環境にプッシュしたことを確認したら、ChromeでWebサイトのホームページに移動し、[!UICONTROL Adobe Experience Cloudデバッガー]を開きます。
2. すべてが機能している場合は、開発環境でのテストと類似したデータが表示されます。この時点で、サイト上のデータを収集するようになっており、レポートへの Adobe Analytics の使用を開始できます。

## トラブルシューティング

**デバッガーにデータが表示されません。**

サイトにアクセスしている間に、ブラウザーのデベロッパーコンソール（通常は F12）を開きます。ページのソースコードを見て、次の条件が満たされていることを確認します。

* コンソールに JavaScript エラーはありません。組織の Web サイトの所有者と協力して、すべての JS エラーが解決されていることを確認します。
* ヘッダーコードが正しく実装されている：ヘッダーコードが `<head>` タグ内にあり、ファイルが存在することを確認してください。
* AppMeasurement ライブラリが存在します：JS ソースに直接移動し、JS ファイルにコードが含まれていることを確認します。表示されない場合は、各環境が作成され、それぞれの環境にライブラリが公開されていることを確認します。
* 干渉プラグイン：一部の Chrome プラグインは、画像リクエストの発動を防ぐことがあります。アドビのサーバーへのデータの送信を停止する可能性のあるプラグインを無効にします。

## 次の手順

これで基本的な実装が設定されました。組織内でのお客様の役割が、詳細を確認するパスに影響を与える可能性があります。

* [ソリューションデザインドキュメントの作成](../prepare/solution-design.md)：カスタム変数の使用方法を計画し、実装に含めます。
* [Analysis Workspace の使用を開始する](/help/analyze/analysis-workspace/home.md)：ツールの主力機能を使用して、Adobe Analytics に直接アクセスします。
