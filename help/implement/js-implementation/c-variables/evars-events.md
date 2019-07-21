---
description: '追加の情報を追跡したいが、十分な変数がない場合は、追加のeVarおよび成功イベントにアクセスできるようになりました '
keywords: Analyticsの導入;evar;events;evars number;eVarの数;イベントの数
seo-description: '追加の情報を追跡したいが、十分な変数がない場合は、追加のeVarおよび成功イベントにアクセスできるようになりました '
seo-title: 追加のeVarおよびイベント
solution: Analytics
title: 追加のeVarおよびイベント
topic: 開発者と導入
uuid: 6f53069b-6941-40f1-9db6-2d1839822b8f
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 追加のeVarおよびイベント

さらに多くのデータを計測したいのに十分な変数がないという場合のために、利用できる eVar および成功イベントの数が増えました。

>[!NOTE]
>
>JavaScript Hコードは、これらの追加のeVarおよびイベントをサポートしていません。

## カスタムディメンションおよびイベントの利用条件 {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Adobe Analytics 製品 |  |  |  |
|---|---|---|---|
| Adobe Analytics - Foundation | 75 prop | 200 eVar | 1000 イベント |
| Adobe Analytics - [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 prop | 200 eVar | 1000 イベント |
| Adobe Analytics - [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 prop | 200 eVar | 1000 イベント |
| Adobe Analytics - [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 prop | 250 eVar | 1000 イベント |

## 変数とイベントの設定 {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* Variables can be populated in the data collection library if you are using these versions of [!DNL AppMeasurement]:

   * AppMeasurement for JavaScript バージョン 1.4 以上
   * AppMeasurement for Flash バージョン 3.9 以上
   * AppMeasurement for Java バージョン 1.2.8 以上
   * AppMeasurement for Silverlight/.NET バージョン 1.4.2 以上
   * AppMeasurement for PHP バージョン 1.2.2 以上

* これより前のバージョンのコードまたは s_code H.* を使用している場合は、コンテキストデータを設定し、処理ルールを使用して変数を設定する必要があります。
* すべてのバージョンのデータ収集コードでイベント 101 ～ 1000 を設定できます。
* 処理ルールを使用し、コンテキストデータや他の変数に基づいて eVar 76 ～ 250 を設定できます。

## よくある質問 {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **すべての Adobe Analytics インターフェイスでこれらの新しい変数を直ちに利用できますか。** これらのインターフェイスは、すぐにアクセスできます。 [!UICONTROL Analysis Workspace]、 [!UICONTROL Reports&amp; Analytics]、 [!UICONTROL Report Builder]、 [!UICONTROL Ad Hoc Analysis]、APIおよび [!UICONTROL Data Workbench]。

* **追加された eVar およびイベントは、自分のデータフィードに自動的に表示されますか。**&#x200B;新しい変数およびイベントを有効にすると、データフィードで利用可能になります。新しい eVar 列は、ユーザーがそれらを含めるよう選択するまで表示されません。しかし、新しいイベントは、有効になるとすぐに event_list 列に表示され、そのイベント ID に対するイベント名がイベント検索テーブルに格納されます。データフィードで取り込んで処理する準備ができるまでは、新しいイベントを有効にしないでください。

* **新しいデータフィード列をリクエストするにはどうすればよいですか。**&#x200B;新しい列をリクエストする方法については、[データフィードの設定](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html)を参照してください。

* **現在 200 個以上の eVar を有効にしている Analytics Ultimate ユーザーが Analytics Prime に戻るとどうなりますか。**&#x200B;アドビによって既存の eVar が無効化されることはありませんが、追加で有効にすることはできなくなります。eVar を無効にすると、有効になっている eVar の数が Analytics Prime の上限である 200 個を下回るまで、該当の eVar を再度有効にすることはできません。

