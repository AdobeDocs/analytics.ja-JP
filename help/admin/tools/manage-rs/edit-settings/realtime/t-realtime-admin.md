---
description: リアルタイムレポートを設定するための管理者の手順です。
title: リアルタイムレポートの設定
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
TQID: https://experienceleague.adobe.com/HTu1UvUUIGK0SzAQWEFBclV-P1JaPCJUp6j5MiYC3A0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 68%

---

# リアルタイムレポートの設定

リアルタイムレポートを設定するための管理者の手順です。

Adobe Analyticsでリアルタイムレポートを設定するには、レポートスイートを選択し、最大3つのレポートを設定します。 デフォルトでは、すべてのユーザーがリアルタイムレポートにアクセスします。

1. リアルタイムレポートを有効にするレポートスイートを選択します。

   **[!UICONTROL Analytics]** / **[!UICONTROL 管理者/ レポートスイート]**&#x200B;に移動します。

1. **[!UICONTROL 設定を編集]** > **[!UICONTROL リアルタイム]**&#x200B;をクリックします。

1. 最大 3 つのレポートに対してリアルタイムデータ収集を設定し、レポートあたり 1 つの指標と 3 つのディメンションまたは分類を使用できます。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/real_time_admin.png)

   サポートされるリアルタイム指標とディメンションについて詳しくは、「[サポートされる指標とディメンション](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md)」を参照してください。

   分類を作成している場合は、定義されているディメンションの下に、それらの分類がインデントして表示されます。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >単一のリアルタイムレポートの場合、ディメンションごとに異なる分類が選択されていても、ディメンションの複製を有効にすることは現在サポートされていません。

   >[!NOTE]
   >
   >「検索キーワード」や「製品」などのディメンションが Adobe Analytics と同じようにリアルタイムで保持されるとは限りません。 永続的ではない指標を選択すると、次の警告が表示されます。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   この最初のレポート設定の後、データのストリーミングが開始されるまでに最大20分かかる場合があります。 その後、データはすぐに利用可能になります。

1. リアルタイムレポートを表示するには、次の場所に移動します。

   **[!UICONTROL Workspace]** > **[!UICONTROL レポート]** > **[!UICONTROL エンゲージメント]** > **[!UICONTROL リアルタイム]**。

