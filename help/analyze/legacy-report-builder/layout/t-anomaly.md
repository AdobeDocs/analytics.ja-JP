---
description: Report Builderで異常値検出リクエストを作成する方法を説明します。
title: 異常値検出リクエストの設定方法
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 72%

---

# 異常値検出リクエストの設定

{{legacy-arb}}

Report Builderで異常値検出リクエストを作成するには：

1. **[!UICONTROL サイト指標]**／**[!UICONTROL トラフィック]**&#x200B;レポートなどで、トレンドレポートを選択します。
1. [!UICONTROL 精度の適用]メニューで、「**[!UICONTROL 日]**」を選択します。

   >[!NOTE]
   >
   >[!UICONTROL 異常値検出]メニューは、「日」の精度を選択した場合にのみ利用できます。選択した期間を問わず、過去 30 日間のデータが統計データのトレーニング期間として使用されます。

1. 日付範囲の設定後、「**[!UICONTROL 次へ]**」をクリックします。

   リクエストウィザード：ステップ 2 / 2 で、**[!UICONTROL 訪問回数]**&#x200B;などの指標を追加します。

   追加した指標の「**[!UICONTROL なし]**」リンクをクリックします。

   ![ 異常値検出、挿入および下限と上限のオプションを挿入して期待することを示すスクリーンショット。](assets/anomaly_select.png)

1. **[!UICONTROL 異常の検出]**／**[!UICONTROL `<selection>`]** を選択します。

   ![ リクエストウィザードのステップ 2 を示すスクリーンショット – トラフィックレポート。](assets/anomaly_visit.png)

   いずれかのオプションを選択すると、元の指標から異常値検出用のコピーが作成されます。例えば、訪問指標の場合、[!UICONTROL 指標]グループに下限訪問指標が追加されます。
1. 「**[!UICONTROL 完了]**」をクリックし、Excel に出力するセルを選択します。

   [異常値検出](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)を参照してください。
