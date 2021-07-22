---
title: Adobe Analytics の実装
description: Adobe Analytics をサイト、プロパティまたはアプリケーションに実装します。
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 83%

---

# Adobe Analytics の実装

![バナー](../../assets/doc_banner_implement.png)

アドビのデータ収集サーバーにデータを送信するには、サイトまたはアプリケーションにコードが必要です。次の手順は、一般的な実装の仕組みを示しています。

1. 訪問者がサイトに訪問すると、Web サーバーへのリクエストが作成されます。
2. サイトの Web サーバーは、ページコード情報を送信し、ページがブラウザーに表示されます。
3. ページが読み込まれ、Analytics JavaScript コードが実行されます。JavaScript コードは、イメージリクエストをアドビデータ収集サーバーに送信します。実装で定義したページデータは、このイメージリクエストのクエリー文字列の一部として送信されます。

4. アドビは、透明なピクセルイメージを返します。
5. Adobe サーバーは、収集したデータを 1 つ以上の&#x200B;*レポートスイート*&#x200B;に格納します。
6. レポートスイートデータは、Web ブラウザーでアクセスできるレポートに入力されます。

   JavaScript コードの実行は迅速におこなわれ、ページ読み込み時間には影響しません。この方法では、ページがキャッシュから取得された場合でも JavaScript コードが実行されるので、訪問者が「**[!UICONTROL リロード]**」または「**[!UICONTROL 戻る]**」をクリックして表示されたページをカウントできます。

Adobe Analytics では、データ収集サーバーにデータを送信するために、Web サイト、モバイルアプリケーションまたはその他のアプリケーション内のコードが必要です。プラットフォームや組織のニーズに応じて、このコードを実装する方法がいくつかあります。

* **タグAdobe Experience Platform**:Adobe Analyticsを実装するための標準化されたお勧めの方法。各ページにローダタグを配置し、データ収集UIを使用して各変数の定義方法を決定します。
* **従来の JavaScript**：Adobe Analytics を実装するために古くから使用されている手動の方法です。実装で使用される変数と設定の概要を説明します。これは、カスタムコードを含むルールを使用するタグ実装で役立ちます。
* **モバイル SDK**：モバイルアプリケーション内からアドビに簡単にデータを送信する専用ライブラリです。

## 主な Analytics 実装記事

* [既存の Adobe Analytics の実装を担当する](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Experience Platformでのタグプロパティの作成](launch/create-analytics-property.md)
* [AppMeasurement のアップデート](appmeasurement-updates.md)

## その他の Analytics ユーザーガイド

[Analytics ユーザーガイド](/help/landing/home.md)

## 主な Analytics リソース

* [カスタマーケアにお問い合わせください](https://helpx.adobe.com/jp/contact/enterprise-support.ec.html)
* [Analytics フォーラム](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics リソース](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
