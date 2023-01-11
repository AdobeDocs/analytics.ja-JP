---
description: 異常値をテーブルまたは線グラフで表示できます。
title: Analysis Workspace での異常値の表示
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: 8be2b622250b1da3ec765592253df2607de67a96
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 16%

---

# Analysis Workspace での異常値の表示

異常値はテーブルまたは折れ線グラフで表示できます。

## テーブルの異常値の表示 {#section_869A87B92B574A38B017A980ED8A29C5}

時系列のフリーフォームテーブルに異常値を表示できます。

1. 列ヘッダーの列設定アイコンを選択し、 [!UICONTROL **異常値**] オプションのリストで「 」が選択されている。 詳しくは、 [列設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. 異常値は、テーブルに次のように表示されます。

   ![](assets/anomaly_detected.png)

   A **暗い灰色の三角形** は、データの異常値が検出された各行の右上隅に表示されます。

   色付きの **縦線** 各行には、期待値が示されます。 色付きの **影付き領域** 各行には、実際の値が示されます。 線（期待値）と影付きの領域（実際の値）の比較によって、異常値があるかどうかが決まります。 (「異常値」の観測は、 [異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

1. 行の右上隅にある灰色の三角形を選択して、異常値に関する詳細を表示します。 これは、実際の値が期待値の上または下に分岐する範囲（パーセンテージ）を示します。

## 折れ線グラフの異常値の表示 {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

折れ線グラフは、異常値を表示できる唯一のビジュアライゼーションです。

折れ線グラフの異常値を表示するには：

1. ビジュアライゼーションヘッダーの設定アイコンを選択し、 [!UICONTROL **異常値を表示**] オプションのリストで「 」が選択されている。 詳しくは、 [線](/help/analyze/analysis-workspace/visualizations/line.md).

1. （オプション）信頼区間でグラフを拡大・縮小するには、ビジュアライゼーションヘッダーの設定アイコンを選択し、次に、オプションを選択します。 **[!UICONTROL 異常値に対して Y 軸のスケールの設定を許可]**.

   グラフが読みにくくなる場合があるので、このオプションはデフォルトでは選択されていません。

1. 設定メニューの外側をクリックして、更新した折れ線グラフを表示します。

   ![](assets/anomaly_linechart.png)

   異常値は、折れ線グラフに次のように表示されます。

   A **白い点** は、データの異常値が検出された場合は常に行に表示されます。 (「異常値」の観測は、 [異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

   この **明るい陰影領域** は、値が発生する信頼帯（期待される範囲）です。 この期待範囲外の値は異常値です。

   折れ線グラフに複数の指標がある場合は、異常値のみが表示され、各異常値の上にマウスポインターを置くと、その指標の信頼帯が表示されます。

   この **点線** は正確な期待値です。

1. 白い点をクリックすると、異常値に関する次の情報が表示されます。

   * 異常値が発生した日付

   * 異常値の生の値

   * 期待値を上回るまたは下回る割合の値。これは緑の実線で表されます。

   * [貢献度分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)を開始するための分析リンク。





