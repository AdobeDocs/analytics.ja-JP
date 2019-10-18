---
description: '[!DNL Activity Map]のリンク収集とユーザーのダウンロードを有効にするためにAnalytics管理者が完了する必要がある手順を説明します。'
seo-description: '[!DNL Activity Map]のリンク収集とユーザーのダウンロードを有効にするためにAnalytics管理者が完了する必要がある手順を説明します。'
seo-title: '[!DNL Activity Map]を有効にする'
solution: Analytics
title: '[!DNL Activity Map]を有効にする'
topic: Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# 有効にする [!DNL Activity Map]{#enable-activity-map}

Explains the steps the Analytics Admin needs to complete to enable [!DNL Activity Map] link collection and user download.

## 手順 1. Update Your AppMeasurement (Javascript) Code to v1.6 (or higher) {#section_5D1586289DF2489289B1B6C1C80C300D}

The [!DNL Activity Map] module is part of the AppMeasurement.js file (located at the top of the file). The AppMeasurement library will load the [!DNL Activity Map] module when instantiated.

[!DNL Activity Map] のデータは、このバージョン以上の AppMeasurement に更新しない限り収集できません。

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

    モジュールを含めることによるコードの変更を視覚的に確認できるように、[実装コードのサンプル](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734)を含めました。[!DNL Activity Map]

1. 実装を検証します。

   1. クリック可能な要素をクリックすると、s_sq という名前の cookie にデータが保存されます。
   1. The [!DNL Activity Map] data can be seen in the query-string on the tracking call. 次に例を示します。

      ```
      …&c.&a.&[!DNL Activity Map].&link=My%20Link&region=My%20Region&page=My%20Page&.[!DNL Activity Map]&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL [!DNL Activity Map]Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## 手順 2：レポートの有 [!DNL Activity Map] 効化 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

First, you need to enable [!DNL Activity Map] reports at a report-suite level.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt;[!DNL Activity Map]]** &gt; **[!UICONTROL [!DNL Activity Map]Reporting]** .
1. [!DNL Activity Map] レポートでリンクデータを収集 [!DNL Activity Map] します。 For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable[!DNL Activity Map]Reports]**.

   この手順により、データの収集が必要な Analytics のディメンションがすべて追加されます。

1. After about an hour, check the [[!DNL Activity Map] Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), which shows all the pages where users clicked on a link.

## 手順 3. Add users to [!DNL Activity Map] access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Click **[!UICONTROL Add Users to Group]**.

   Admin Console のグループ管理ページが表示されます。

1. [このグループにユーザーを追加し](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) 、「グ **[!UICONTROL ループを保存]**」。

1. This allow your Admin users to download [!DNL Activity Map] from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  管理者以外のユーザーが[!DNL Activity Map]をダウンロードできるようにする場合は、ツール/従来のClickMapインストールに対する権限を提供する新しいユーザ <span class="uicontrol"> ーグ </span> ループ <span class="uicontrol"> を作成する必要がありま </span>す。 その後、管理者以外のユーザーをこのグループに追加できます。 [!DNL Activity Map]アクセスと組み合わされたこのレベルのアクセス許可は、ツールをダウンロードして使用するための包括的なアクセス許可を提供します。 
</note>
