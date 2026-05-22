---
title: 開発実装の検証と実稼動環境への公開
description: Adobe Experience Platform のタグを使用して、Adobe Analytics を本番環境にデプロイする方法を説明します。
feature: Tags
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/FpJRwRs9GXGTzUY52vWqC5Ddej-I3mh2ASC6YKphNRI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 635
ht-degree: 65%

---

# 開発実装の検証と実稼動環境への公開

タグライブラリが実稼働環境にプッシュされると、組織は Adobe Analytics を使用して基本的なレポートの取り込みを開始できます。

## 前提条件

[Analytics 実装を開発環境にデプロイする](deploy-dev.md)：このページの手順をおこなうには、Analytics 実装を開発環境に公開する必要があります。

## CX Enterprise デバッガーを使用して開発実装を検証する

CX Enterprise debuggerは、ページに存在するすべてのCX Enterprise タグを表示する拡張機能です。

1. [Chrome](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob)またはFirefoxの拡張機能をインストールします。
2. タグを実装した開発用 web サイトに移動します。
3. ブラウザーでAdobe CX Enterprise debugger アイコンをクリックします。
4. すべてが適切に実装されている場合は、Adobe Analytics、タグ、Adobe Experience Cloud Visitor ID サービス内にコンテンツが表示されます。

## ステージング／実稼動環境に開発環境の実装をデプロイする

データが表示されていることを検証したら、実装をサイトのライブバージョンにプッシュできます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. サイトに実装するタグプロパティをクリックします。
1. 「**[!UICONTROL 公開]**」タブをクリックし、開発列でライブラリを探します。
1. ライブラリのドロップダウンリストをクリックし、**[!UICONTROL 承認用に送信]**&#x200B;を選択します。 モーダルウィンドウで「**[!UICONTROL 送信]**」をクリックします。
1. ライブラリのドロップダウンリスト（現在は「送信済み」列）をもう一度クリックし、**[!UICONTROL ステージング用にビルド]**&#x200B;を選択します。
1. しばらくすると、ライブラリの黄色のライトが緑色に変わり、ビルドが正常に完了したことを示します。
1. ライブラリのドロップダウンリストをもう一度クリックし、**[!UICONTROL 公開用に承認]**&#x200B;を選択します。
1. ライブラリのドロップダウンリスト（[!UICONTROL Approved]列）をもう一度クリックし、**[!UICONTROL Build and Publish to Production]**&#x200B;を選択します。
1. 「環境」タブに移動し、「**[!UICONTROL 本番環境]**」をクリックします。
1. 実稼動インストールコードをコピーし、web サイトの所有者に提供します。 サイトの本番環境にこのコードを実装するように要求します。

## 実稼動環境の実装を検証します。

本番用サイトのデータが表示されていることを確認し、Adobe Analytics の正式なデータ収集を開始します。

1. web サイトの所有者からタグコードを実稼動環境にプッシュしたことを確認したら、Chromeでweb サイトのホームページに移動し、Adobe CX Enterprise debuggerを開きます。
2. すべてが機能している場合は、開発環境でのテストと類似したデータが表示されます。 この時点で、サイト上のデータを収集するようになっており、レポートへの Adobe Analytics の使用を開始できます。

## トラブルシューティング

**デバッガーにデータが表示されません。**

サイトにアクセスしている間に、ブラウザーのデベロッパーコンソール（通常は F12）を開きます。 ページのソースコードを見て、次の条件が満たされていることを確認します。

* コンソールに JavaScript エラーはありません。 組織の Web サイトの所有者と協力して、すべての JS エラーが解決されていることを確認します。
* ヘッダーコードが正しく実装されている：ヘッダーコードが `<head>` タグ内にあり、ファイルが存在することを確認してください。
* AppMeasurement ライブラリが存在します：JS ソースに直接移動し、JS ファイルにコードが含まれていることを確認します。 表示されない場合は、各環境が作成され、それぞれの環境にライブラリが公開されていることを確認します。
* 拡張機能の干渉：広告ブロッカーなどの一部の拡張機能は、画像リクエストの実行を妨げる可能性があります。 Adobeへのデータ送信を停止する可能性がある拡張機能を無効にします。

## 次の手順

これで基本的な実装が設定されました。組織内でのお客様の役割が、詳細を確認するパスに影響を与える可能性があります。

* [ソリューションデザインドキュメントの作成](../prepare/solution-design.md)：カスタム変数の使用方法を計画し、実装に含めます。
* [Analysis Workspace の使用を開始する](/help/analyze/analysis-workspace/home.md)：ツールの主力機能を使用して、Adobe Analytics に直接アクセスします。
