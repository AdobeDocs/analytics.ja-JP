---
description: リアルタイムレポートを設定するための管理者の手順です。
title: リアルタイムレポートの設定
topic: Admin tools
uuid: f48692a0-77c0-4ee4-b3ec-eaa842d06ac8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# リアルタイムレポートの設定

リアルタイムレポートを設定するための管理者の手順です。

Reports &amp; Analytics 内でリアルタイムレポートを設定する手順は、レポートスイートを選択する操作と、そのレポートスイートに対して最大 3 つのレポートを設定する操作で構成されます。

1. リアルタイムレポートを有効にするレポートスイートを選択します。

   **[!UICONTROL Analytics]**／**[!UICONTROL レポート]**／**[!UICONTROL すべてのレポートを表示／サイト指標]**／**[!UICONTROL リアルタイム]**&#x200B;に移動し、上部のドロップダウンからレポートスイートを選択します。

   ![](assets/report_suite_selector.png)

   リアルタイムレポート用に設定されていないレポートスイートのリアルタイムレポートを表示しようとすると、メッセージが表示されます。このメッセージから、レポートスイートの設定を実行できます。

   ![](assets/rep_suite_not_set_up.png)

1. **[!UICONTROL 設定]**（歯車アイコン）をクリックして、Report Suite Manager を実行します。

   （**[!UICONTROL Analytics]**／**[!UICONTROL 管理者／レポートスイート]**／**[!UICONTROL 設定を編集]**／**[!UICONTROL リアルタイム]**&#x200B;から Report Suite Manager にアクセスすることもできます）

1. 「**[!UICONTROL リアルタイムの処理を有効にする]**」設定をオンにします。
1. 最大 3 つのレポートに対してリアルタイムデータ収集を設定し、レポートあたり 1 つの指標と 3 つのディメンションまたは分類を使用できます。

   ![](assets/real_time_admin.png)

   サポートされるリアルタイム指標とディメンションについて詳しくは、「[サポートされる指標とディメンション](/help/admin/admin/realtime/realtime-metrics.md)」を参照してください。

   分類を作成している場合は、定義されているディメンションの下に、それらの分類がインデントして表示されます。

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >単一のリアルタイムレポートの場合、ディメンションごとに異なる分類が選択されていても、ディメンションの複製を有効にすることは現在サポートされていません。

   分類の詳細については、「[分類について](/help/components/c-classifications2/c-classifications.md)」を参照してください。

   >[!NOTE]
   >
   >「検索キーワード」や「製品」などのディメンションが Adobe Analytics と同じようにリアルタイムで保持されるとは限りません。永続的ではない指標を選択すると、次の警告が表示されます。

   ![](assets/warning_dimensions.png)

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL レポートを保存して表示]**」をクリックします。

   この最初のレポート設定の後、データのストリーミングが開始されるまでに最大 20 分間かかることがあります。それ以降はデータをすぐに使用できます。リアルタイムレポートの表示については、[リアルタイムレポートの実行](https://marketing.adobe.com/resources/help/en_US/sc/user/reports_realtime.html)を参照してください。

1. デフォルトでは、すべてのユーザーがリアルタイムレポートにアクセスします。
