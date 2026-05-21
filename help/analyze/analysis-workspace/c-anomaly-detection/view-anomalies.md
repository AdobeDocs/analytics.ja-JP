---
description: Analysis Workspaceでデータの異常値を表示および分析する方法について説明します。
title: 異常値の表示
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
TQID: https://experienceleague.adobe.com/FFrOBGUYdaBiIzutrZNlcKcLD8jUiT2aCpGd252rVlU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: c67272a6-888e-425e-9e97-a87304637eedid: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 448
ht-degree: 45%

---

# 異常値を表示

Analysis Workspaceの異常値は、表または折れ線グラフで表示できます。

## テーブルの異常値の表示 {#section_869A87B92B574A38B017A980ED8A29C5}

時系列フリーフォームテーブルの異常値を表示できます。

1. 列ヘッダーの「![設定](/help/assets/icons/Setting.svg)」を選択し、オプションのリストで「**[!UICONTROL 異常値]**」オプションが選択されていることを確認します。 詳しくは、[列設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)を参照してください。

1. 異常値は、テーブルに次のように表示されます。

   ![異常値が検出されました](assets/anomaly-detected.png)

   データの異常値が検出された各行の右上隅に◥が表示されます。

   各行➋の&#x200B;**色付きの垂直線**&#x200B;は、期待される値を示します。 各行➊の&#x200B;**色付きシェーディング領域**&#x200B;は、実際の値を示します。 線（期待値）と影になっている部分（実際の値）の比較方法は、異常値があるかどうかを決定します。 （観察は、[異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)で説明されている高度な統計的手法に基づいて異常と見なされます）。

1. 行の右上隅にある◥を選択して、異常値の詳細を表示します。 これは、実際の値が期待値の上下にどの程度乖離しているかを（パーセントで）示します。
1. [貢献度分析を開く](run-contribution-analysis.md)を選択して、貢献度分析を開始します。

## 折れ線グラフの異常値の表示

折れ線グラフは、異常値を表示できる唯一のビジュアライゼーションです。

折れ線グラフで異常値を表示するには：

1. ビジュアライゼーションヘッダーで「![設定](/help/assets/icons/Setting.svg)」を選択し、オプションのリストで「[!UICONTROL **異常値を表示**]」オプションが選択されていることを確認します。 詳しくは、[折れ線グラフ](/help/analyze/analysis-workspace/visualizations/line.md)を参照してください。

1. （オプション）信頼区間でチャートを拡大/縮小できるようにするには、ビジュアライゼーションヘッダーで「![設定](/help/assets/icons/Setting.svg)」を選択し、「**[!UICONTROL 異常値をY軸に拡大/縮小]**」オプションを選択します。

   グラフがわかりにくくなる可能性があるので、このオプションは、デフォルトでは選択されていません。

   異常値は、折れ線グラフに次のように表示されます。

   ![異常値が行の可視化を検出しました](assets/anomaly-detected-line.gif)

   データの異常値が検出されると、線上に&#x200B;**白い点**&#x200B;が表示されます。 （観察は、[異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)で説明されている高度な統計的手法に基づいて異常と見なされます）。

   **薄く影になっている部分**&#x200B;は、値が発生するはずの信頼帯または期待範囲です。 この期待範囲外の値は、異常値です。

   折れ線グラフに複数の指標がある場合、異常値のみが表示され、その指標の信頼帯を表示するには、各異常値の上にマウスポインターを置く必要があります。

   **点線**&#x200B;は、正確な期待値です。

1. 異常（白い点）を選択して、次の情報を表示します。

   * 異常が発生した日付。

   * 異常値の生の値。

   * 期待値の上下のパーセント値。緑の実線で表されます。

   * 貢献度分析を開始するための&#x200B;**[!UICONTROL Analyze]** リンク






