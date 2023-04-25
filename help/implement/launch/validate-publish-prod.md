---
title: 開発実装の検証と実稼動環境への公開
description: Adobe Experience Platform のタグを使用して、Adobe Analytics を実稼動環境にデプロイする方法を説明します。
feature: Launch Implementation
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 72%

---

# 開発実装の検証と実稼動環境への公開

タグライブラリが実稼働環境にプッシュされると、組織は Adobe Analytics を使用して基本的なレポートの取り込みを開始できます。

## 前提条件

[Analytics 実装を開発環境にデプロイする](deploy-dev.md)：このページの手順をおこなうには、Analytics 実装を開発環境に公開する必要があります。

## Experience Cloud デバッガーを使用した開発環境の実装の検証

Experience Cloudデバッガーは、ページに存在するすべてのExperience Cloudタグを表示する拡張機能です。

1. 次のいずれかの拡張機能をインストールします。 [クロム](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) または [Firefox](https://addons.mozilla.org/ja/firefox/addon/adobe-experience-platform-dbg/).
2. タグを実装した開発用 web サイトに移動します。
3. ブラウザーでAdobe Experience Cloud Debugger アイコンをクリックします。
4. すべてが正しく実装されている場合は、Adobe Analytics、タグおよびAdobe Experience Cloud訪問者 ID サービス内にコンテンツが表示されます。

## ステージング／実稼動環境に開発環境の実装をデプロイする

データが表示されていることを検証したら、実装を本番用サイトにプッシュできます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. サイトに実装するタグプロパティをクリックします。
1. 「**[!UICONTROL 公開]**」タブをクリックし、開発列でライブラリを探します。
1. ライブラリのドロップダウンリストをクリックし、「 」を選択します。 **[!UICONTROL 承認用に送信]**. モーダルウィンドウで「**[!UICONTROL 送信]**」をクリックします。
1. ライブラリのドロップダウンリスト（「送信済み」列に表示）を再度クリックし、「 」を選択します。 **[!UICONTROL ステージング用にビルド]**.
1. しばらくすると、ライブラリの黄色のライトが緑色に変わり、ビルドが正常に完了したことを示します。
1. ライブラリのドロップダウンリストを再度クリックし、「 」を選択します。 **[!UICONTROL 公開の承認]**.
1. ライブラリのドロップダウンリストを再度クリックします ( [!UICONTROL 承認済み] 列 ) を選択し、 **[!UICONTROL ビルドして実稼動環境にパブリッシュ]**.
1. 「環境」タブに移動し、「**[!UICONTROL 実稼動環境]**」をクリックします。
1. 実稼動用インストールコードをコピーし、Web サイトの所有者に提供します。 サイトの実稼動環境にこのコードを実装するように要求します。

## 実稼動環境の実装を検証します。

本番用サイトのデータが表示されていることを確認し、Adobe Analytics の正式なデータ収集を開始します。

1. Web サイトの所有者がタグコードを実稼動にプッシュしたことを確認したら、Chrome で web サイトのホームページに移動し、[!UICONTROL Adobe Experience Cloud Debugger]を開きます。
2. すべてが機能している場合は、開発環境でのテストと類似したデータが表示されます。この時点で、サイト上のデータを収集するようになっており、レポートへの Adobe Analytics の使用を開始できます。

## トラブルシューティング

**デバッガーにデータが表示されません。**

サイトにアクセスしている間に、ブラウザーのデベロッパーコンソール（通常は F12）を開きます。ページのソースコードを見て、次の条件が満たされていることを確認します。

* コンソールに JavaScript エラーはありません。組織の Web サイトの所有者と協力して、すべての JS エラーが解決されていることを確認します。
* ヘッダーコードが正しく実装されている：ヘッダーコードが `<head>` タグ内にあり、ファイルが存在することを確認してください。
* AppMeasurement ライブラリが存在します：JS ソースに直接移動し、JS ファイルにコードが含まれていることを確認します。表示されない場合は、各環境が作成され、それぞれの環境にライブラリが公開されていることを確認します。
* 干渉拡張機能：広告ブロッカーなどの一部の拡張は、イメージリクエストの実行を防ぐ可能性があります。 データのAdobeへの送信を停止する可能性のある拡張機能を無効にします。

## 次の手順

これで基本的な実装が設定されました。組織内でのお客様の役割が、詳細を確認するパスに影響を与える可能性があります。

* [ソリューションデザインドキュメントの作成](../prepare/solution-design.md)：カスタム変数の使用方法を計画し、実装に含めます。
* [Analysis Workspace の使用を開始する](/help/analyze/analysis-workspace/home.md)：ツールの主力機能を使用して、Adobe Analytics に直接アクセスします。
