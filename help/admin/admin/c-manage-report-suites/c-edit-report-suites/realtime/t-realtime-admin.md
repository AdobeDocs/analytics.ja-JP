---
description: リアルタイムレポートを設定するための管理者の手順です。
title: リアルタイムレポートの設定
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: f1dde3a475fe1276fd9abbe1bdafd6723701f2cb
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 77%

---

# リアルタイムレポートの設定

リアルタイムレポートを設定するための管理者の手順です。

Adobe Analyticsでリアルタイムレポートを設定する手順は、レポートスイートを選択する操作と、そのレポートスイートに対して最大 3 つのレポートを設定する操作で構成されます。 デフォルトでは、すべてのユーザーがリアルタイムレポートにアクセスします。

1. リアルタイムレポートを有効にするレポートスイートを選択します。

   に移動します。 **[!UICONTROL Analytics]** > **[!UICONTROL 管理者/レポートスイート]**.

1. クリック **[!UICONTROL 設定を編集]** > **[!UICONTROL リアルタイム]**.

1. 最大 3 つのレポートに対してリアルタイムデータ収集を設定し、レポートあたり 1 つの指標と 3 つのディメンションまたは分類を使用できます。

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   サポートされるリアルタイム指標とディメンションについて詳しくは、「[サポートされる指標とディメンション](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)」を参照してください。

   分類を作成している場合は、定義されているディメンションの下に、それらの分類がインデントして表示されます。

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >単一のリアルタイムレポートの場合、ディメンションごとに異なる分類が選択されていても、ディメンションの複製を有効にすることは現在サポートされていません。

   分類の詳細については、「[分類について](/help/components/classifications/c-classifications.md)」を参照してください。

   >[!NOTE]
   >
   >「検索キーワード」や「製品」などのディメンションが Adobe Analytics と同じようにリアルタイムで保持されるとは限りません。永続的ではない指標を選択すると、次の警告が表示されます。

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   この最初のレポート設定の後、データのストリーミングが開始されるまでに最大 20 分間かかることがあります。それ以降、データは直ちに使用可能になります。

1. リアルタイムレポートを表示するには、次の場所に移動します。

   **[!UICONTROL Workspace]** > **[!UICONTROL レポート]** > **[!UICONTROL エンゲージメント]** > **[!UICONTROL リアルタイム]**.

