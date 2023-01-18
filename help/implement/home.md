---
title: Adobe Analytics の実装
description: Adobe Analytics をサイト、プロパティ、アプリケーションに実装します。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: d2c291f7db465034ffadc4a2c1caf9639caf2a1d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 79%

---

# Adobe Analytics の実装

![バナー](../../assets/doc_banner_implement.png)

以下は、Adobe Analytics の概説ビデオです。

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

アドビのデータ収集サーバーにデータを送信するには、サイトまたはアプリケーションにコードが必要です。以下の手順は、一般的な実装の仕組みを示しています。


1. 訪問者がサイトにアクセスすると、web サーバーへのリクエストが作成されます。
2. サイトの Web サーバーは、ページコード情報を送信し、ページがブラウザーに表示されます。
3. ページが読み込まれ、Analytics JavaScript コードが実行されます。
4. JavaScript コードは、1 x 1 ピクセルのイメージリクエストをAdobeデータ収集サーバーに送信します。 実装で定義したページデータは、このイメージリクエストのクエリー文字列の一部として送信されます。
5. Adobeのデータ収集サーバーは、要求されたイメージを返します。
6. Adobeサーバーは、収集したデータを解析してレポートスイートに保存します。
7. レポートスイートデータは、Web ブラウザーでアクセスできるレポートに入力されます。


Adobeは、プラットフォームと組織のニーズに応じて、このコードを実装するいくつかの方法を提供します。

* **Web SDK 拡張機能**:Adobe Analyticsの現在の、標準化された、および推奨される実装方法。 Web SDK 拡張機能を Adobe Experience Platform データ収集にインストールし、各ページでローダータグを使用して、組織にとって使いやすい形式で Adobe Experience Platform Edge にデータを送信します。Experience Edge は、受信したデータを正しい形式で Adobe Analytics に転送します。
* **Web SDK**:タグを使用しない場合は、サイトに Web SDK ライブラリを手動で読み込むことができます。 各ページで Web SDK ライブラリを参照し、目的のトラッキングコールを Adobe Experience Edge に送信します。
* **Adobe Analytics 拡張機能**：Adobe Analytics 拡張機能を Adobe Experience Platform データ収集にインストールします。各ページにローダータグを配置し、Analytics 拡張機能を使用して、各変数の定義方法を決定します。
* **従来の JavaScript**：Adobe Analytics を実装するためにこれまで使用されてきた手動の方法です。実装で使用される変数や設定の概要を説明します。カスタムコードを含んだルールを使用した実装に役に立ちます。
* **モバイル SDK**：モバイルアプリケーション内からアドビに簡単にデータを送信する専用ライブラリです。

## 主な Analytics 実装記事

* [既存の Adobe Analytics の実装を担当する](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Experience Platform でのタグプロパティの作成](launch/create-analytics-property.md)
* [AppMeasurement のアップデート](appmeasurement-updates.md)

## その他の Analytics ユーザーガイド

[Analytics ユーザーガイド](https://experienceleague.adobe.com/docs/analytics.html?lang=ja)

## 主な Analytics リソース

* [カスタマーケアへのお問い合わせ](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=ja#support)
* [Analytics フォーラム](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics リソース](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=ja)
* [Experience League](https://experienceleague.adobe.com/?lang=ja#dashboard/learning)
