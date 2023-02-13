---
description: 異常値をテーブルまたは線グラフで表示できます。
title: Analysis Workspace での異常値の表示
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: bc56f3567d2285d063ef35f316e22699bdcf151d
workflow-type: ht
source-wordcount: '467'
ht-degree: 100%

---

# Analysis Workspace での異常値の表示

異常値はテーブルまたは折れ線グラフで表示できます。

## テーブルの異常値の表示 {#section_869A87B92B574A38B017A980ED8A29C5}

時系列フリーフォームテーブルの異常値を表示できます。

1. 列ヘッダーの列設定アイコンを選択してから、オプションのリストで「[!UICONTROL **異常値**]」オプションが選択されていることを確認します。詳しくは、[列設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)を参照してください。

1. 設定メニューの外側をクリックして、更新されたテーブルを表示します。

   ![](assets/anomaly_detected.png)

1. 異常値は、テーブルに次のように表示されます。

   データの異常値が検出された各行の右上隅に、**ダークグレーの三角形**&#x200B;が表示されます。

   各行の色付きの&#x200B;**縦線**&#x200B;は、期待値を示します。各行の色付きの&#x200B;**影になっている部分**&#x200B;は、実際の値を示します。線（期待値）と影になっている部分（実際の値）の比較方法は、異常値があるかどうかを決定します。（観測は、[異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)に記載されている高度な統計的手法に基づいて異常と見なされます。）

1. 行の右上隅にあるグレーの三角形を選択して、異常値に関する詳細を表示します。これは、実際の値が期待値の上下にどの程度乖離しているかを（パーセントで）示します。

## 折れ線グラフの異常値の表示 {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

折れ線グラフは、異常値を表示できる唯一のビジュアライゼーションです。

折れ線グラフで異常値を表示するには：

1. ビジュアライゼーションヘッダーで設定アイコンを選択してから、オプションのリストで「[!UICONTROL **異常値を表示**]」オプションが選択されていることを確認します。詳しくは、[折れ線グラフ](/help/analyze/analysis-workspace/visualizations/line.md)を参照してください。

1. （オプション）信頼区間でグラフを拡大／縮小するには、ビジュアライゼーションヘッダーで設定アイコンを選択してから、「**[!UICONTROL 異常値で Y 軸のスケールの設定を可能にする]**」オプションを選択します。

   グラフがわかりにくくなる可能性があるので、このオプションは、デフォルトでは選択されていません。

1. 設定メニューの外側をクリックして、更新された折れ線グラフを表示します。

   ![](assets/anomaly_linechart.png)

   異常値は、折れ線グラフに次のように表示されます。

   データの異常値が検出されると、線上に&#x200B;**白い点**&#x200B;が表示されます。（観測は、[異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)に記載されている高度な統計的手法に基づいて異常と見なされます。）

   **薄く影になっている部分**&#x200B;は、値が発生するはずの信頼帯または期待範囲です。この期待範囲外の値は、異常値です。

   折れ線グラフに複数の指標がある場合、異常値のみが表示され、その指標の信頼帯を表示するには、各異常値の上にマウスポインターを置く必要があります。

   **点線**&#x200B;は、正確な期待値です。

1. 異常値（白い点）をクリックして、次の情報を表示します。

   * 異常値が発生した日付

   * 異常値の生の値

   * 期待値を上回るまたは下回る割合の値。これは緑の実線で表されます。

   * [貢献度分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)を開始するための分析リンク。





