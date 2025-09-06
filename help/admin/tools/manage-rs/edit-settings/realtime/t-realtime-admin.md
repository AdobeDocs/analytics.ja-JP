---
description: リアルタイムレポートを設定するための管理者の手順です。
title: リアルタイムレポートの設定
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 76%

---

# リアルタイムレポートの設定

リアルタイムレポートを設定するための管理者の手順です。

Adobe Analyticsでのリアルタイムレポートの設定では、レポートスイートを選択し、最大 3 つのレポートを設定します。 デフォルトでは、すべてのユーザーがリアルタイムレポートにアクセスします。

1. リアルタイムレポートを有効にするレポートスイートを選択します。

   **[!UICONTROL Analytics]**/**[!UICONTROL 管理者/レポートスイート]** に移動します。

1. **[!UICONTROL 設定を編集]**/**[!UICONTROL リアルタイム]** をクリックします。

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
   >「検索キーワード」や「製品」などのディメンションが Adobe Analytics と同じようにリアルタイムで保持されるとは限りません。永続的ではない指標を選択すると、次の警告が表示されます。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   この最初のレポート設定の後、データのストリーミングが開始されるまでに最大 20 分間かかることがあります。それ以降は、データを直ちに使用できます。

1. リアルタイムレポートを表示するには、次に移動します。

   **[!UICONTROL Workspace]**/**[!UICONTROL レポート]**/**[!UICONTROL エンゲージメント]**/**[!UICONTROL リアルタイム]**。

