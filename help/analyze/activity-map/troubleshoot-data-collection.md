---
title: Activity Mapデータ収集のトラブルシューティング
description: イメージリクエストでActivity Mapデータが表示されない理由の特定
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---


# Activity Mapデータ収集のトラブルシューティング

Activity Mapディメンションのデータが表示されない場合は、このページを使用して理由を判断してください。

## デバッガーを使用したデータ収集の確認

最初に、AppMeasurementがActivity Mapデータを正しく収集していることを確認します。

1. [Adobe Experience CloudデバッガーChrome Extensionをダウンロードしてインストールします](https://docs.adobe.com/content/help/ja-JP/debugger/using/experience-cloud-debugger.html)。
2. Webページに移動し、リンクをクリックします。
3. 後続のページが読み込まれたら、デバッガーを開きます。 との間にActivity Mapコンテキストデータ変数が挟まれていることを検証し `activitymap.` ま `.activitymap`す。

![デバッガーデータ](assets/debugger.png)

## Activity Mapデータが存在しない理由として考えられる

次の各項目を確認し、Activity Mapコンポーネントが存在することを確認します。

* **AppMeasurementバージョン**:Activity Mapはv1.6以降でサポートされています。 最新の安定版のAppMeasurementにアップグレードすると、多くのエッジケースの問題が解決されます。
* **Activity Mapモジュール**:モジュールが `AppMeasurement_Module_Activity_Map``AppMeasurement.js` ファイル内に存在するかどうかを確認します。 導入でAdobe Experience Platform Launchを使用している場合、「 **[!UICONTROL リンクトラッキング]** 」でAnalytics拡張機能を設定する際に、「ClickMapを **[!UICONTROL 有効にする]**」がオンになっていることを確認してください。
* **Cookie`s_sq`**:Activity Mapは、データ収集用の `s_sq` cookieに依存します。
   * 変数が正しく設定されていることを確認します（特に、やなどの地域ドメインの場合） `cookieDomainPeriods``*.co.uk``*.co.jp`。
   * 変数が目的の値に設定されていることを確認し `linkInternalFilters` ます。 クリックされたリンクが内部フィルターと一致しない場合、Activity Mapはそのリンクを離脱リンクと見なし、データを収集しません。
* **実行中のActivity Mapオーバーレイ**:Activity Mapオーバーレイが有効な場合、WebページのクリックデータはAppMeasurementで追跡されません。
