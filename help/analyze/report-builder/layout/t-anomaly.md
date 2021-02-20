---
description: Report Builder で異常値検出関連データを抽出する手順です。
title: 異常値検出リクエストの設定
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 100%

---


# 異常値検出リクエストの設定

Report Builder で異常値検出関連データを抽出する手順です。

1. **[!UICONTROL サイト指標]**／**[!UICONTROL トラフィック]**&#x200B;レポートなどで、トレンドレポートを選択します。
1. [!UICONTROL 精度の適用]メニューで、「**[!UICONTROL 日]**」を選択します。

   >[!NOTE]
   >
   >[!UICONTROL 異常値検出]メニューは、「日」の精度を選択した場合にのみ利用できます。選択した期間を問わず、過去 30 日間のデータが統計データのトレーニング期間として使用されます。

1. 日付範囲の設定後、「**[!UICONTROL 次へ]**」をクリックします。

   手順の結果 1リクエストウィザード：ステップ 2 / 2 で、**[!UICONTROL 訪問回数]**&#x200B;などの指標を追加します。

   手順の結果 1追加した指標の「**[!UICONTROL なし]**」リンクをクリックします。

   ![手順の結果](assets/anomaly_select.png)

1. **[!UICONTROL 異常の検出]**／**[!UICONTROL `<selection>`]** を選択します。

   ![ステップ情報](assets/anomaly_visit.png)

   いずれかのオプションを選択すると、元の指標から異常値検出用のコピーが作成されます。例えば、訪問指標の場合、[!UICONTROL 指標]グループに下限訪問指標が追加されます。
1. 「**[!UICONTROL 完了]**」をクリックし、Excel に出力するセルを選択します。

   [異常値検出](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)を参照してください。
