---
description: Report Builderで異常値検出リクエストを作成する方法について説明します。
title: 異常値検出リクエストの設定方法
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
TQID: https://experienceleague.adobe.com/9qyfB3mtj7QKDNLL1PRrQ2-3lzrb19-7gL4rnfxbph4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: c67272a6-888e-425e-9e97-a87304637eed
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 54%

---

# 異常値検出リクエストの設定

{{legacy-arb}}

Report Builderで異常値検出リクエストを作成するには：

1. **[!UICONTROL サイト指標]**／**[!UICONTROL トラフィック]**&#x200B;レポートなどで、トレンドレポートを選択します。
1. [!UICONTROL 精度の適用]メニューで、「**[!UICONTROL 日]**」を選択します。

   >[!NOTE]
   >
   >[!UICONTROL 異常値検出]メニューは、「日」の精度を選択した場合にのみ利用できます。 選択した期間を問わず、過去 30 日間のデータが統計データのトレーニング期間として使用されます。

1. 日付範囲の設定後、「**[!UICONTROL 次へ]**」をクリックします。

   リクエストウィザード：ステップ 2 / 2 で、**[!UICONTROL 訪問回数]**&#x200B;などの指標を追加します。

   追加した指標の「**[!UICONTROL なし]**」リンクをクリックします。

   ![異常値検出を示すスクリーンショット。次に、下限と上限のオプションを挿入してから挿入します。](assets/anomaly_select.png)

1. **[!UICONTROL 異常の検出]**／**[!UICONTROL `<selection>`]** を選択します。

   リクエストウィザードの手順2 - トラフィックレポートを示す![&#x200B; スクリーンショット。](assets/anomaly_visit.png)

   これらのオプションのいずれかを選択すると、元の指標の異常値検出コピーが作成されます。 例えば、訪問指標の場合、下限訪問指標が[!UICONTROL 指標] グループに追加されます。
1. 「**[!UICONTROL 完了]**」をクリックし、Excel に出力するセルを選択します。

   [異常値検出](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)を参照してください。
