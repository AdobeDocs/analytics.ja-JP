---
title: Activity Mapデータ収集のトラブルシューティング
description: イメージリクエストにActivity Mapデータが表示されない理由の特定
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Activity Mapデータ収集のトラブルシューティング

Activity Mapディメンションのデータが表示されない場合は、このページを使用して理由を判断してください。

## デバッガーを使用してデータ収集を確認する

まず、AppMeasurement が正しくActivity Mapデータを収集するようにします。

1. をダウンロードしてインストールする [Adobe Experience Cloud Debugger Chrome 拡張機能](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja).
2. Web ページに移動し、リンクをクリックします。
3. 後続のページが読み込まれたら、デバッガーを開きます。 次の間にActivity Mapコンテキストデータ変数が挟まれていることを検証します。 `activitymap.` および `.activitymap`:

![デバッガーデータ](assets/debugger.png)

## Activity Mapデータが存在しない理由

次の各点を確認して、Activity Mapコンポーネントが存在することを確認します。

* **AppMeasurement バージョン**:Activity Mapは v1.6 以降でサポートされています。 AppMeasurement の最新の安定したバージョンにアップグレードすると、多くのエッジケースの問題が解決されます。
* **Activity Mapモジュール**:をチェックします。 `AppMeasurement_Module_Activity_Map` モジュールが `AppMeasurement.js` ファイル。 実装でAdobe Experience Platformを使用してデータを収集している場合は、 **[!UICONTROL ClickMapを有効にする]** は、以下で Analytics 拡張機能を設定する際にチェックされます。 **[!UICONTROL リンクトラッキング]**.
* **この `s_sq` cookie**:Activity Mapは `s_sq` cookie（データ収集用）
   * 必ず `cookieDomainPeriods` 変数が正しく設定されること ( 特に `*.co.uk` または `*.co.jp`.
   * 必ず `linkInternalFilters` 変数に設定されます。 クリックされたリンクが内部フィルターに一致しない場合、Activity Mapはそのリンクを出口リンクと見なし、データを収集しません。
* **Activity Mapオーバーレイ実行中**:Activity Mapオーバーレイが有効な場合、Web ページのクリックデータは AppMeasurement で追跡されません。
