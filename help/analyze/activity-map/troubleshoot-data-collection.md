---
title: Activity Mapのデータ収集のトラブルシューティング
description: イメージリクエストにActivity Mapデータが表示されない理由の特定
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 3%

---

# Activity Mapのデータ収集のトラブルシューティング

Activity Mapディメンションのデータが表示されない場合は、このページを使用して理由を判断してください。

## デバッガーを使用したデータ収集の確認

まず、AppMeasurementが正しくActivity Mapデータを収集するようにします。

1. [Adobe Experience Cloud Debugger Chrome拡張機能](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)をダウンロードしてインストールします。
2. Webページに移動し、リンクをクリックします。
3. 後続のページが読み込まれたら、デバッガーを開きます。 `activitymap.`と`.activitymap`の間にActivity Mapコンテキストデータ変数が挟まれていることを検証します。

![デバッガーデータ](assets/debugger.png)

## Activity Mapデータが存在しない理由

次の各点を確認して、Activity Mapコンポーネントが存在することを確認します。

* **AppMeasurementバージョン**:Activity Mapはv1.6以降でサポートされています。AppMeasurementの最新の安定バージョンにアップグレードすると、多くのエッジケースの問題が解決されます。
* **Activity Mapモジュール**:モジュールがファ `AppMeasurement_Module_Activity_Map` イル内に存在するかどうかを確 `AppMeasurement.js` 認します。実装でAdobe Experience PlatformClickMap収集(Launch)を使用する場合は、**[!UICONTROL リンクトラッキング]**&#x200B;でAnalytics拡張機能を設定する際に、「**[!UICONTROL データを有効にする]**」がオンになっていることを確認してください。
* **`s_sq` cookie**&#x200B;の場合：Activity Mapは、データ収 `s_sq` 集のcookieに依存します。
   * 特に`*.co.uk`や`*.co.jp`などの地域ドメインでは、`cookieDomainPeriods`変数が正しく設定されていることを確認してください。
   * `linkInternalFilters`変数が目的の値に設定されていることを確認します。 クリックされたリンクが内部フィルターと一致しない場合、Activity Mapはそのリンクを出口リンクと見なし、データを収集しません。
* ****&#x200B;を実行するActivity Mapオーバーレイ：Activity Mapオーバーレイが有効な場合、WebページのクリックデータはAppMeasurementで追跡されません。
