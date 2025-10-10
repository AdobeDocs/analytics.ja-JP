---
description: リアルタイムレポートを設定するための管理者の手順です。
title: リアルタイムレポートの設定
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 74%

---

# リアルタイムレポートの設定

次の情報には、リアルタイムレポートを設定するための管理手順が含まれています。

これは、レポートスイートの選択と、そのレポートスイートに対する最大 3 つのレポートの設定で構成されます。

1. リアルタイムレポートを有効にするレポートスイートを選択します。

   1. Analysis Workspaceで、「[!UICONTROL **Workspace**]」タブを選択し、[!UICONTROL **レポート**]/[!UICONTROL **エンゲージメント**]/**[!UICONTROL リアルタイム]** を選択します。

   1. 上部のドロップダウンからレポートスイートを選択します。

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report_suite_selector.png)

      リアルタイムレポート用に設定されていないレポートスイートのリアルタイムレポートを表示しようとすると、メッセージが表示されます。このメッセージから、レポートスイートの設定を実行できます。

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/rep_suite_not_set_up.png)

1. **[!UICONTROL 設定]** を選択して、[!UICONTROL  レポートスイートマネージャー ] を実行します。

   （**[!UICONTROL Analytics]**／**[!UICONTROL 管理者／レポートスイート]**／**[!UICONTROL 設定を編集]**／**[!UICONTROL リアルタイム]**&#x200B;から Report Suite Manager にアクセスすることもできます）

1. 「**[!UICONTROL リアルタイムの処理を有効にする]**」設定をオンにします。
1. 最大 3 つのレポートに対してリアルタイムデータ収集を設定し、レポートあたり 1 つの指標と 3 つのディメンションまたは分類を使用できます。

   ![](assets/real_time_admin.png)

   サポートされるリアルタイム指標とディメンションについて詳しくは、「[サポートされる指標とディメンション](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md)」を参照してください。

   分類を作成している場合は、定義されているディメンションの下に、それらの分類がインデントして表示されます。

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >単一のリアルタイムレポートの場合、ディメンションごとに異なる分類が選択されていても、ディメンションの複製を有効にすることは現在サポートされていません。

   >[!NOTE]
   >
   >「検索キーワード」や「製品」などのディメンションが Adobe Analytics と同じようにリアルタイムで保持されるとは限りません。永続的ではない指標を選択すると、次の警告が表示されます。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. **[!UICONTROL 保存]** または **[!UICONTROL 保存してレポートを表示]** を選択します。

   この最初のレポート設定の後、データのストリーミングが開始されるまでに最大 20 分間かかることがあります。それ以降は、データを直ちに使用できます。

1. デフォルトでは、すべてのユーザーがリアルタイムレポートにアクセスします。
