---
description: リアルタイムレポートを設定するための管理者の手順です。
seo-description: リアルタイムレポートを設定するための管理者の手順です。
seo-title: リアルタイムレポートの設定
solution: Analytics
title: リアルタイムレポートの設定
topic: 管理ツール
uuid: f48692a0-77c0-4ee4-b3ec-eaa842d06ac8
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# リアルタイムレポートの設定

リアルタイムレポートを設定するための管理者の手順です。

Reports &amp; Analytics 内でリアルタイムレポートを設定する手順は、レポートスイートを選択する操作と、そのレポートスイートに対して最大 3 つのレポートを設定する操作で構成されます。

1. リアルタイムレポートを有効にするレポートスイートを選択します。

   **[!UICONTROL Analytics]** /レポート **[!UICONTROL /レ]** ポートを表示/サイト指標 **[!UICONTROL /す]****** べてのリアルタイムレポートスイートに移動し、上部のドロップダウンから選択します。

   ![](assets/report_suite_selector.png)

   リアルタイムレポート用に設定されていないレポートスイートのリアルタイムレポートを表示しようとすると、メッセージが表示されます。このメッセージから、レポートスイートの設定を実行できます。

   ![](assets/rep_suite_not_set_up.png)

1. Click **[!UICONTROL Configure]** (gear icon) to run the [!UICONTROL Report Suite Manager].

   (Also available under **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Real-Time]**.)

1. Turn on the **[!UICONTROL Enable Real-Time]** setting.
1. 最大 3 つのレポートに対してリアルタイムデータ収集を設定し、レポートあたり 1 つの指標と 3 つのディメンションまたは分類を使用できます。

   ![](assets/real_time_admin.png)

   サポートされるリアルタイム指標とディメンションについて詳しくは、「サポートされる指標とデ [ィメンション」を参照してくださ](/help/admin/admin/realtime/realtime-metrics.md)い。

   分類を作成している場合は、定義されているディメンションの下に、それらの分類がインデントして表示されます。

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >単一のリアルタイムレポートでは、ディメンションごとに異なる分類が選択されている場合でも、現在、ディメンションの複製を有効にする機能はサポートされていません。

   分類の詳細については、「分類について」を参 [照してください](/help/components/c-classifications2/c-classifications.md)。

   >[!NOTE]
   >
   >「検索キーワード」や「製品」などのディメンションは、Adobe Analyticsの他の場所と同様に、リアルタイムで保持されません。 永続的ではない指標を選択すると、次の警告が表示されます。

   ![](assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]** or **[!UICONTROL Save and View Report]**.

   この最初のレポート設定の後、データのストリーミングが開始されるまでに最大 20 分間かかることがあります。それ以降はデータをすぐに使用できます。リアルタイムレポートの表示については、「[リアルタイムレポートの実行](https://marketing.adobe.com/resources/help/en_US/sc/user/reports_realtime.html)」を参照してください。

1. デフォルトでは、すべてのユーザーがリアルタイムレポートにアクセスします。
