---
description: リアルタイムレポートを設定するための管理者の手順です。
title: リアルタイムレポートの設定
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
TQID: https://experienceleague.adobe.com/wmZj-F8P4ectiMUnpy9yYT-pviys2m2aBGAVtP5kNNI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 68%

---

# リアルタイムレポートの設定

次の情報には、リアルタイムレポートを設定するための管理手順が含まれています。

これには、レポートスイートを選択し、最大3つのレポートを設定します。

1. リアルタイムレポートを有効にするレポートスイートを選択します。

   1. Analysis Workspaceで、「[!UICONTROL **Workspace**]」タブを選択し、[!UICONTROL **レポート**] > [!UICONTROL **エンゲージメント**] > **[!UICONTROL リアルタイム]**」を選択します。

   1. 上部のドロップダウンからレポートスイートを選択します。

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report_suite_selector.png)

      リアルタイムレポート用に設定されていないレポートスイートのリアルタイムレポートを表示しようとすると、メッセージが表示されます。このメッセージから、レポートスイートの設定を実行できます。

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/rep_suite_not_set_up.png)

1. **[!UICONTROL 設定]**&#x200B;を選択して、[!UICONTROL  レポートスイートマネージャー]を実行します。

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
   >「検索キーワード」や「製品」などのディメンションが Adobe Analytics と同じようにリアルタイムで保持されるとは限りません。 永続的ではない指標を選択すると、次の警告が表示されます。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. **[!UICONTROL 保存]**&#x200B;または&#x200B;**[!UICONTROL 保存してレポートを表示]**&#x200B;を選択します。

   この最初のレポート設定の後、データのストリーミングが開始されるまでに最大20分かかる場合があります。 その後、データはすぐに利用可能になります。

1. デフォルトでは、すべてのユーザーがリアルタイムレポートにアクセスします。
