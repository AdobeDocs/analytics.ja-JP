---
description: Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者が行う手順について説明します。
seo-description: Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者が行う手順について説明します。
seo-title: Activity Map の有効化
solution: Analytics
title: Activity Map の有効化
topic: Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Activity Map の有効化{#enable-activity-map}

Activity Map のリンクコレクションおよびユーザーダウンロードを有効にするために Analytics 管理者が行う手順について説明します。

## 手順 1.Update Your AppMeasurement (Javascript) Code to v1.6 (or higher) {#section_5D1586289DF2489289B1B6C1C80C300D}

Activity Map モジュールは、AppMeasurement.js ファイルの一部です（ファイルの先頭にあります）。AppMeasurement ライブラリは、インスタンス化の際に Activity Map を読み込みます。

Activity Map のデータは、このバージョン以上の AppMeasurement に更新しない限り収集できません。

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Activity Map モジュールを含めることによるコードの変更を視覚的に確認できるように、[実装コードのサンプル](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md)を含めました。

1. 実装を検証します。

   1. クリック可能な要素をクリックすると、s_sq という名前の cookie にデータが保存されます。
   1. Activity Map データは、トラッキングコール時のクエリ文字列で確認できます。次に例を示します。

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## 手順 2：Enable Activity Map reports {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

まず、レポートスイートレベルで Activity Map レポートを有効にする必要があります。

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt; Activity Map]** &gt; **[!UICONTROL Activity Map Reporting]** .
1. リンクデータが Activity Map レポートに収集されます。For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   この手順により、データの収集が必要な Analytics のディメンションがすべて追加されます。

1. 約 1 時間後に、[Activity Map ページレポート](/help/analyze/activity-map/activitymap-reporting-analytics.md)を確認すると、ユーザーがリンクをクリックしたページがすべて表示されます。

## 手順 3.Add users to Activity Map access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Click **[!UICONTROL Add Users to Group]**.

   Admin Console のグループ管理ページが表示されます。

1. [このグループにユーザーを追加し](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) 、「グ **[!UICONTROL ループを保存]**」。

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

> [!NOTE] 管理者以外のユーザーがActivity mapをダウンロードできるようにする場合は、「ツール」と「従来のClickMapのインストール」に対する権限を提供する新しいユーザーグループを作成します。 このレベルの権限は、Activity mapアクセスと組み合わされて、ツールをダウンロードして使用する権限を提供します。
