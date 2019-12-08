---
description: report builder で異常値検出リクエストを作成する手順です。
title: 異常値検出リクエストの設定
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 異常値検出リクエストの設定

Report Builder で異常値検出関連データを抽出する手順です。

1. **サイト指標**／**[!UICONTROL トラフィック]**&#x200B;レポートなどで、トレンドレポートを選択します。
1. In the [!UICONTROL Apply Granularity] menu, select **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. 選択した期間を問わず、過去 30 日間のデータが統計データのトレーニング期間として使用されます。

1. After configuring date ranges, click **[!UICONTROL Next]**.

   手順の結果 1On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   手順の結果 1For the added metric, click the **[!UICONTROL None]** link.

   ![手順の結果](assets/anomaly_select.png)

1. Select **[!UICONTROL Anomaly Detection]** &gt; **[!UICONTROL `<selection>`]**.

   ![ステップ情報](assets/anomaly_visit.png)

   いずれかのオプションを選択すると、元の指標から異常値検出用のコピーが作成されます。例えば、訪問指標の場合、[!UICONTROL 指標]グループに下限訪問指標が追加されます。
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   See [Anomaly Detection](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) for definitions.
