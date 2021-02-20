---
title: Adobe Analytics の実装
description: Adobe Analytics をサイト、プロパティまたはアプリケーションに実装します。
translation-type: tm+mt
source-git-commit: 34ccd89d0ac4223af87b36a48e778fb678d5cd59
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 100%

---


# Adobe Analytics の実装

![バナー](../../assets/doc_banner_implement.png)

アドビのデータ収集サーバーにデータを送信するには、サイトまたはアプリケーションにコードが必要です。次の手順は、一般的な実装の仕組みを示しています。

1. 訪問者がサイトに訪問すると、Web サーバーへのリクエストが作成されます。
2. サイトの Web サーバーは、ページコード情報を送信し、ページがブラウザーに表示されます。
3. ページが読み込まれ、Analytics JavaScript コードが実行されます。JavaScript コードは、イメージリクエストをアドビデータ収集サーバーに送信します。実装で定義したページデータは、このイメージリクエストのクエリー文字列の一部として送信されます。

4. アドビは、透明なピクセルイメージを返します。
5. アドビのサーバーは、収集したデータを&#x200B;*レポートスイート*&#x200B;に保存します。
6. レポートスイートデータは、Web ブラウザーでアクセスできるレポートに入力されます。

   JavaScript コードの実行は迅速におこなわれ、ページ読み込み時間には影響しません。この方法では、ページがキャッシュから取得された場合でも JavaScript コードが実行されるので、訪問者が「**[!UICONTROL リロード]**」または「**[!UICONTROL 戻る]**」をクリックして表示されたページをカウントできます。

Adobe Analytics では、データ収集サーバーにデータを送信するために、Web サイト、モバイルアプリケーションまたはその他のアプリケーション内のコードが必要です。プラットフォームや組織のニーズに応じて、このコードを実装する方法がいくつかあります。

* **Adobe Experience Platform Launch**：Adobe Analytics を実装するための標準化されたお勧めの方法です。各ページにローダータグを配置し、Launch のインターフェイスを使用して、各変数の定義方法を決定します。
* **Dynamic Tag Management**：Launch の前に使用されていた方法です。DTM は、似たようなインターフェイスを使用して Analytics を実装しますが、今後は更新されず、柔軟ではありません。アドビでは、Adobe Analytics の実装には Launch を使用することをお勧めします。
* **従来の JavaScript**：Adobe Analytics を実装するために古くから使用されている手動の方法です。実装で使用される変数および設定の概要を説明します。カスタムコードを含むルールを使用する Launch 実装で役立ちます。
* **モバイル SDK**：モバイルアプリケーション内からアドビに簡単にデータを送信する専用ライブラリです。

## 主な Analytics 実装記事

* [既存の Adobe Analytics の実装を担当する](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Experience Platform Launch でのプロパティの作成](launch/create-analytics-property.md)
* [AppMeasurement のアップデート](appmeasurement-updates.md)

## その他の Analytics ユーザーガイド

[Analytics ユーザーガイド](/help/landing/home.md)

## 主な Analytics リソース

* [カスタマーケアにお問い合わせください](https://helpx.adobe.com/jp/contact/enterprise-support.ec.html)
* [Analytics フォーラム](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics リソース](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
