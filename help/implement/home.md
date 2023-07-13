---
title: Adobe Analytics の実装
description: Adobe Analytics をサイト、プロパティ、アプリケーションに実装します。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: bef853934683f647e05d42e1a751217c8f9b5dc4
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 85%

---

# Adobe Analytics の実装

![バナー](../../assets/doc_banner_implement.png)

アドビのデータ収集サーバーにデータを送信するには、サイトまたはアプリケーションにコードが必要です。以下の手順は、一般的な実装の仕組みを示しています。

1. 訪問者がサイトにアクセスすると、web サーバーへのリクエストが作成されます。
2. サイトの Web サーバーは、ページコード情報を送信し、ページがブラウザーに表示されます。
3. ページが読み込まれ、Analytics JavaScript コードが実行されます。
JavaScript コードは、イメージリクエストをアドビデータ収集サーバーに送信します。実装で定義したページデータは、このイメージリクエストのクエリ文字列の一部として送信されます。

4. アドビは、透明なピクセルイメージを返します。
5. Adobe サーバーは、収集したデータを 1 つ以上の&#x200B;*レポートスイート*&#x200B;に格納します。
6. レポートスイートデータは、Web ブラウザーでアクセスできるレポートに入力されます。

JavaScript コードの実行は迅速におこなわれ、ページ読み込み時間には影響しません。この方法では、ページがキャッシュから取得された場合でも JavaScript コードが実行されるので、訪問者が「**[!UICONTROL リロード]**」または「**[!UICONTROL 戻る]**」をクリックして表示されたページをカウントできます。

Adobe Analytics では、データ収集サーバーにデータを送信するために、Web サイト、モバイルアプリケーションまたはその他のアプリケーション内のコードが必要です。プラットフォームや組織のニーズに応じて、このコードを実装する方法がいくつかあります。

## Web サイトの実装方法

**Web サイト**&#x200B;では、次の実装方法を使用できます。

* **Web SDK 拡張機能**：新規顧客向けに Adobe Analytics を実装するための標準化されたお勧めの方法です。のインストール **Adobe Experience Platform Web SDK 拡張機能** (Adobe Experience Platform Data Collection) **タグ**&#x200B;を使用し、各ページでローダタグを使用して、データをAdobe Experience Platformに送信する **Edge Network** 組織に便利な形式で。 Edge Network は、受信したデータを正しい形式で Adobe Analytics に転送します。
  ![Web SDK 拡張機能](./assets/websdk-extension-implementation.png)
詳しくは、 [Adobe Experience Platform Web SDK 拡張機能を使用したAdobe Analyticsの実装方法です。](./aep-edge/overview.md)を参照してください。

* **Web SDK**：Adobe Experience Platform データ収集を使用しない場合は、Web SDK ライブラリを手動でサイトに読み込むことができます。各ページで Web SDK ライブラリ（`alloy.js`）を参照し、必要なトラッキングコールを組織にとって便利な形式で Adobe Experience Platform **Edge Network** に送信します。Edge Network は、受信したデータを正しい形式で Adobe Analytics に転送します。
  ![Web SDK](./assets/websdk-implementation.png)
詳しくは、 [Adobe Experience Platform Web SDK を使用したAdobe Analyticsの実装方法](./aep-edge/overview.md) を参照してください。


* **Analytics 拡張機能**：**Adobe Analytics 拡張機能**&#x200B;を Adobe Experience Platform データ収集&#x200B;**タグ**にインストールします。各ページにローダータグを配置し、Adobe Analytics 拡張機能を使用して、各変数の定義方法を決定します。タグの便利さを望むが、Edge Network インフラストラクチャを使用しない場合は、この実装方法を使用します。
  ![Adobe Analytics拡張機能](./assets/analytics-extension-implementation.png)
詳しくは、 [Analytics 拡張機能を使用したAdobe Analyticsの実装方法](launch/overview.md) を参照してください。

* **従来の JavaScript**：これまで使用されてきた、手動で Adobe Analytics を実装する方法です。各ページで AppMeasurement ライブラリ（`AppMeasurement.js`）を参照し、実装で使用する変数と設定の概要について説明します。
  ![レガシー JavaScript を使用したAdobe Analyticsの実装方法](./assets/appmeasurement-implementation.png)
この実装方法は、カスタムコードを使用した実装で役に立ちますが、を使用する場合にお勧めします。

   * [Activity Map データ](../analyze/activity-map/activity-map.md)。

     >[!INFO]
     >
     >最新の Web SDK を使用して、Activity Map がサポートされています。詳しくは、[Activity Map を有効にする](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)を参照してください。

   * [ストリーミングメディア測定](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=ja)

   * [ライブストリーム API またはライブストリームトリガー](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。

   * [AMP ページトラッキング](./other/amp.md)

  詳しくは、[JavaScript 版 AppMeasurement を使用した Adobe Analytics の実装](js/overview.md)を参照してください。

次の決定フローは、実装方法の選択に役立つ場合があります。

![実装方法を選択するためのデシジョンツリー（この節で説明）。](./assets/decision-tree.png)


>[!TIP]
>
>現在の状況に基づいて実装を選択する際のアドバイスとベストプラクティスについては、アドビにお問い合わせください。

## モバイルアプリの実装方法

**モバイルアプリ**&#x200B;では、次の実装方法を使用できます。

* **Mobile SDK 拡張機能**：モバイルアプリに Adobe Analytics を実装するための標準化されたお勧めの方法です。専用ライブラリを使用して、モバイルアプリ内からアドビにデータを簡単に送信できます。Adobe Experience Platform データ収集&#x200B;**タグ**&#x200B;に **Adobe Experience Platform Mobile SDK 拡張機能**&#x200B;をインストールし、アプリに正しいコードを実装してライブラリを読み込んで、拡張機能を登録し、タグ設定を読み込みます。これにより、組織にとって便利な形式で Adobe Experience Platform **Edge Network** にデータが送信されます。Experience Edge は、受信したデータを正しい形式で Adobe Analytics に転送します。
  ![Mobile SDK 拡張機能](./assets/mobilesdk-extension.png)

  詳しくは、[Adobe Experience Platform Mobile SDK を使用した Adobe Analytics の実装](../implement/aep-edge/mobile-sdk/overview.md)を参照してください。

* **Analytics 拡張機能**：Adobe Experience Platform データ収集&#x200B;**タグ**&#x200B;に **Adobe Analytics 拡張機能**をインストールし、アプリケーションに正しいコードを実装してライブラリを読み込み、拡張機能を登録、タグ設定をロードします。各変数の定義方法は、Analytics 拡張機能を使用して決定します。Adobe Experience Platform データ収集の便利さを望むが、アドビの Experience Platform Edge Network インフラストラクチャを使用しない場合は、この実装方法を使用します。
  ![Analytics 拡張機能](./assets/mobilesdk-analytics-extension.png)

  詳しくは、[Analytics 拡張機能を使用した Adobe Analytics の実装](../implement/aep-edge/mobile-sdk/overview.md)を参照してください。


>[!CAUTION]
>
>バージョン 4 の Mobile SDK のサポートは 2021年8月31日（PT）に終了しました。詳しくは、[バージョン 4 モバイル SDK サポート終了に関する FAQ](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/)（英語）を参照してください。

## 主な Analytics 実装関連の記事

* [既存の Adobe Analytics の実装を担当する](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Experience Platform でのタグプロパティの作成](launch/create-analytics-property.md)
* [AppMeasurement のアップデート](appmeasurement-updates.md)

## その他の Analytics ユーザーガイド

[Analytics ユーザーガイド](https://experienceleague.adobe.com/docs/analytics.html?lang=ja)

## 主な Analytics リソース

* [カスタマーケアへのお問い合わせ](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=ja#support)
* [Analytics フォーラム](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=ja)
* [Adobe Analytics リソース](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=ja)
