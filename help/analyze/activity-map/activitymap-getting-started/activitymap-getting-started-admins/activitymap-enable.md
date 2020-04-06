---
description: Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。
title: Activity Map の有効化
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Activity Map の有効化 {#enable-activity-map}

Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者がおこなう必要がある手順について説明します。

## 手順 1.AppMeasurement（JavaScript）コードを v1.6 以上に更新 {#section_5D1586289DF2489289B1B6C1C80C300D}

アクティビティマップモジュールは、AppMeasurement.jsファイルの一部です（ファイルの上部にあります）。 AppMeasurementライブラリは、インスタンス化時にアクティビティマップモジュールを読み込みます。

アクティビティマップのデータは、このバージョン（またはそれ以降）のAppMeasurementに更新しない限り収集できません。

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/ja_JP/sc/implement/js_implementation.html).

   実装コードのサン [プルを含め](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) 、アクティビティマップモジュールを含めることでコードに加えられた変更を視覚化できるようにしました。

1. 実装の検証:

   1. クリック可能な要素をクリックすると、s_sqという名前のcookieにデータが保存されます。
   1. アクティビティマップデータは、トラッキングコールのクエリ文字列で確認できます。 次に例を示します。

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width=&quot;400px&quot;}

## 手順 2：Activity Map レポートを有効にする {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

まず、レポートスイートレベルで Activity Map レポートを有効にする必要があります。

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites >[select report suite]> Edit Settings > Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. リンクデータが Activity Map レポートに収集されます。For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   この手順では、データを収集するために必要なすべてのAnalyticsディメンションを追加します。

1. 約1時間後に、 [アクティビティマップページレポートを確認し](/help/analyze/activity-map/activitymap-reporting-analytics.md)、ユーザがリンクをクリックしたすべてのページを表示します。

## 手順 3.ユーザーを Activity Map アクセスグループに追加 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. クリック **[!UICONTROL Add Users to Group]**.

   Admin Console のグループ管理ページが表示されます。

1. [このグル追加ープおよびに対するユーザー](https://marketing.adobe.com/resources/help/ja_JP/reference/groups.html)**[!UICONTROL Save Group]**。

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

>[!NOTE] 管理者以外のユーザーが Activity Map をダウンロードしたい場合、新規ユーザーグループを作成し、「ツール」および「レガシー ClickMap のインストール」の権限を付与します。Activity Map アクセスと組み合わせたこのレベルの権限は、ツールをダウンロードおよび使用する権限を付与します。
