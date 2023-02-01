---
title: Adobe Analytics の実装
description: Adobe Analytics をサイト、プロパティ、アプリケーションに実装します。
feature: Implementation Basics
source-git-commit: d9a5d8a15b9e108af795cdfb7ed5481d51311328
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 40%

---

# Adobe Analytics の実装

![バナー](../../assets/doc_banner_implement.png)

アドビのデータ収集サーバーにデータを送信するには、サイトまたはアプリケーションにコードが必要です。以下の手順は、一般的な実装の仕組みを示しています。


1. 訪問者がサイトにアクセスすると、web サーバーへのリクエストが作成されます。
2. サイトの Web サーバーは、ページコード情報を送信し、ページがブラウザーに表示されます。
3. ページが読み込まれ、Analytics JavaScript コードが実行されます。JavaScript コードは、イメージリクエストをAdobeデータ収集サーバーに送信します。 実装で定義したページデータは、このイメージリクエストのクエリー文字列の一部として送信されます。

4. アドビは、透明なピクセルイメージを返します。
5. Adobe サーバーは、収集したデータを 1 つ以上の&#x200B;*レポートスイート*&#x200B;に格納します。
6. レポートスイートデータは、Web ブラウザーでアクセスできるレポートに入力されます。

JavaScript コードの実行は迅速におこなわれ、ページ読み込み時間には影響しません。この方法では、ページがキャッシュから取得された場合でも JavaScript コードが実行されるので、訪問者が「**[!UICONTROL リロード]**」または「**[!UICONTROL 戻る]**」をクリックして表示されたページをカウントできます。

Adobe Analytics では、データ収集サーバーにデータを送信するために、Web サイト、モバイルアプリケーションまたはその他のアプリケーション内のコードが必要です。プラットフォームや組織のニーズに応じて、このコードを実装する方法がいくつかあります。

## Web サイトの実装方法

の **web サイト**&#x200B;に値を入力する場合、次の実装方法を使用できます。

* **Web SDK 拡張機能**:新規のお客様にAdobe Analyticsを実装するための標準化されたお勧めの方法です。 のインストール **AEP Web SDK 拡張機能** (Adobe Experience Platform Data Collection) **タグ**&#x200B;を使用し、各ページでローダタグを使用して、データをAdobe Experience Platformに送信する **Edge Network** 組織に便利な形式で。 Edge Network は、受信データを正しい形式でAdobe Analyticsに転送します。
   ![Web SDK 拡張機能](./assets/websdk-extension-implementation.png)
詳しくは、 [Adobe Experience Platform Web SDK 拡張機能を使用したAdobe Analyticsの実装](./aep-edge/overview.md) を参照してください。

* **Web SDK**：Adobe Experience Platform データ収集を使用しない場合は、Web SDK ライブラリを手動でサイトに読み込むことができます。Web SDK ライブラリ (`alloy.js`) をクリックし、目的のトラッキングコールをAdobe Experience Platformに送信します。 **Edge Network** 組織に便利な形式で。 Edge Network は、受信データを正しい形式でAdobe Analyticsに転送します。
   ![Web SDK](./assets/websdk-implementation.png)
詳しくは、 [Adobe Experience Platform Web SDK を使用したAdobe Analyticsの実装](./aep-edge/overview.md) を参照してください。


* **Analytics 拡張機能**:のインストール **Adobe Analytics拡張機能** (Adobe Experience Platform Data Collection) **タグ**. 各ページにローダータグを配置し、 Adobe Analytics拡張機能を使用して各変数の定義方法を決定します。 タグの便利さを望むが、Edge ネットワークインフラストラクチャを使用しない場合は、この実装方法を使用します。
   ![Adobe Analytics拡張機能](./assets/analytics-extension-implementation.png)
詳しくは、 [Analytics 拡張機能を使用したAdobe Analyticsの実装](launch/overview.md) を参照してください。

* **従来の JavaScript**：Adobe Analytics を実装するためにこれまで使用されてきた手動の方法です。AppMeasurement ライブラリ (`AppMeasurement.js`) をクリックし、実装で使用される変数と設定の概要を示します。
   ![レガシー JavaScript](./assets/appmeasurement-implementation.png)
この実装方法は、カスタムコードを使用した実装で役に立ちますが、を使用する場合にお勧めします。

   * [クリックレベルの activity map データ](../analyze/activity-map/activity-map.md),

   * [ストリーミングメディア測定](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=ja),

   * [livestream API または livestreamトリガー](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md),

   * [AMP ページトラッキング](./other/amp.md)
   詳しくは、 [JavaScript 版 AppMeasurement を使用したAdobe Analyticsの実装](js/overview.md) を参照してください。

次の決定フローは、実装方法の選択に役立つ場合があります。

![決定木](./assets/decision-tree.png)


>[!TIP]
>
>現在の状況に基づいて実装を選択する際のアドバイスとベストプラクティスについては、Adobeにお問い合わせください。

## モバイルアプリの実装方法

の **モバイルアプリ**&#x200B;に値を入力する場合、次の実装方法を使用できます。

* **Mobile SDK 拡張機能**:モバイルアプリにAdobe Analyticsを実装するための標準化されたお勧めの方法です。 専用のライブラリを使用して、モバイルアプリ内からAdobeに簡単にデータを送信できます。 のインストール **Adobe Experience Platform Mobile SDK 拡張機能** (Adobe Experience Platform Data Collection) **タグ** ライブラリを読み込み、拡張機能を登録し、タグ設定を読み込むには、アプリに正しいコードを実装します。 これにより、Adobe Experience Platformにデータが送信されます **Edge Network** 組織に便利な形式で。 Experience Edge は、受信したデータを正しい形式で Adobe Analytics に転送します。
   ![Mobile SDK 拡張機能](./assets/mobilesdk-extension.png)

   詳しくは、 [Adobe Experience Platform Mobile SDK を使用したAdobe Analyticsの実装](../implement/aep-edge/mobile-sdk/overview.md) を参照してください。

* **Analytics 拡張機能**:のインストール **Adobe Analytics拡張機能** (Adobe Experience Platform Data Collection) **タグ**を参照し、ライブラリを読み込むための正しいコードをアプリケーションに実装し、拡張機能を登録してタグ設定を読み込みます。 各変数の定義方法は、Analytics 拡張機能を使用して決定します。 Adobe Experience Platformのデータ収集の便利さを期待するが、AdobeのExperience Platformエッジネットワークインフラストラクチャを使用しない場合は、この実装方法を使用します。
   ![Analytics 拡張機能](./assets/mobilesdk-analytics-extension.png)

   詳しくは、 [Analytics 拡張機能を使用したAdobe Analyticsの実装](../implement/aep-edge/mobile-sdk/overview.md) を参照してください。


>[!CAUTION]
>
>バージョン 4 モバイル SDK のサポートは 2021 年 8 月 31 日に終了しました。 詳しくは、[バージョン 4 モバイル SDK サポート終了 FAQ](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/)（英語）を参照してください。

## 主な Analytics 実装記事

* [既存の Adobe Analytics の実装を担当する](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Experience Platform でのタグプロパティの作成](launch/create-analytics-property.md)
* [AppMeasurement のアップデート](appmeasurement-updates.md)

## その他の Analytics ユーザーガイド

[Analytics ユーザーガイド](https://experienceleague.adobe.com/docs/analytics.html?lang=ja)

## 主な Analytics リソース

* [カスタマーケアへのお問い合わせ](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=ja#support)
* [Analytics フォーラム](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=ja)
* [Adobe Analytics リソース](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
