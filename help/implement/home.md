---
title: Adobe Analytics の実装
description: Adobe Analyticsをサイト、プロパティまたはアプリケーションに実装します。
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Adobe Analytics の実装

![バナー](../../assets/doc_banner_implement.png)

アドビのデータ収集サーバーにデータを送信するには、サイトまたはアプリにコードが必要です。 次の手順は、一般的な実装の仕組みを示しています。

1. 訪問者がサイトに訪問すると、Web サーバーへのリクエストが作成されます。
2. サイトの Web サーバーは、ページコード情報を送信し、ページがブラウザーに表示されます。
3. ページが読み込まれ、Analytics JavaScript コードが実行されます。JavaScriptコードは、イメージリクエストのAdobeデータ収集サーバーを送信します。 実装で定義したページデータは、このイメージリクエストのクエリ文字列の一部として送信されます。

4. Adobe は、透明なピクセルイメージを返します。
5. アドビのサーバーは、収集したデータをレポートスイ *ートに保存しま*&#x200B;す。
6. レポートスイートデータは、Web ブラウザーでアクセスできるレポートに入力されます。

   JavaScript コードの実行は迅速におこなわれ、ページ読み込み時間には影響しません。この方法では、ページがキャッシュから取得された場合でも JavaScript コードが実行されるので、訪問者が「**[!UICONTROL リロード]**」または「**[!UICONTROL &#x200B;戻る]**」をクリックして表示されたページをカウントできます。

Adobe Analyticsでは、データ収集サーバーにデータを送信するために、Webサイト、モバイルアプリまたはその他のアプリケーション内のコードが必要です。 プラットフォームや組織のニーズに応じて、このコードを実装する方法がいくつかあります。

* **Adobe Experience Platform Launch**:Adobe Analyticsを実装するための標準化された推奨される方法です。 各ページにローダータグを配置し、Launch のインターフェイスを使用して、各変数の定義方法を決定します。
* **Dynamic Tag Management**:Launchの前身。 DTM は、似たようなインターフェイスを使用して Analytics を実装しますが、今後は更新されず、柔軟ではありません。アドビでは、Adobe Analytics の実装には Launch を使用することをお勧めします。
* **レガシーJavaScript**:Adobe Analyticsを導入するための過去の手動の方法です。 実装で使用される変数および設定の概要を説明します。カスタムコードを含むルールを使用する Launch 実装で役立ちます。
* **モバイルSDK**:モバイルアプリ内からアドビに簡単にデータを送信する専用ライブラリ。

## 主な Analytics 実装記事

* [Adobe Debugger](validate/debugger.md)
* [Experience Platform Launch でのプロパティの作成](launch/create-analytics-property.md)
* [AppMeasurementの更新](appmeasurement-updates.md)

## その他の Analytics ユーザーガイド

[Analytics ユーザーガイド](/help/landing/home.md)

## 主な Analytics リソース

* [カスタマーケアにお問い合わせください](https://helpx.adobe.com/contact/enterprise-support.ec.html)
* [Analytics フォーラム](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics リソース](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
