---
description: フィルターを適用してフォールアウトレポートを作成する手順について説明します。
title: リクエストウィザードを使用したフォールアウトレポートのフィルタリング
topic: Report builder
uuid: 269e900e-23bd-48d8-9bac-69e3167a9c18
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# リクエストウィザードを使用したフォールアウトレポートのフィルタリング

フィルターを適用してフォールアウトレポートを作成する手順について説明します。

この例では、ページのフォールアウトレポートを示します。

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. 適切なレポートスイートを選択します。
1. In the tree view on the left, select **[!UICONTROL Paths]** &gt; **[!UICONTROL Page]** &gt; **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. 適切な日付範囲を [設定します](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)。
1. 「**[!UICONTROL Next]**」をクリックします。
1. In Step 2 of the Wizard, under **[!UICONTROL Row Labels]**, click the **[!UICONTROL Define Checkpoints]** link. （フォールアウトレポートでは、パターンが事前に適用されているパスレポートとは異なり、常にパスエレメントを定義する必要があります）。

   ![](assets/define_checkpoints.png)

1. Select the **[!UICONTROL Filter]** option.

1. In the **[!UICONTROL Define Site Section Fallout Checkpoints]** dialog, define checkpoints from a range of cells or from a list. Then click **[!UICONTROL OK]**.
1. セルの範囲またはリストのいずれから選択するかを決定します。
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. 3 ～ 8 件のチェックポイントを定義できます(Search for available elements by clicking **[!UICONTROL More]**.)

   For more information on refining the filter, see [Filter Dimensions](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md). 1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. Click **[!UICONTROL OK]** three times, then click **[!UICONTROL Finish]**.

   レポートが更新されます。
