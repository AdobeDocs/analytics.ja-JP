---
description: 異常値はテーブルまたは折れ線グラフで表示できます。
title: Analysis Workspace での異常値の表示
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 57%

---

# Analysis Workspace での異常値の表示

異常値はテーブルまたは折れ線グラフで表示できます。

## テーブルの異常値の表示 {#section_869A87B92B574A38B017A980ED8A29C5}

時系列フリーフォームテーブルの異常値を表示できます。

1. 列ヘッダーの ![ 設定 ](/help/assets/icons/Setting.svg) を選択し、オプションのリストで **[!UICONTROL 異常値]** オプションが選択されていることを確認します。 詳しくは、[列設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)を参照してください。

1. 異常値は、テーブルに次のように表示されます。

   ![ 異常値が検出されました ](assets/anomaly-detected.png)

   データの異常値が検出された各行の右上隅に ◥ が表示されます。

   各行の **色付きの縦線** は、期待値 ➋ 示します。 各行の **色付きの影付き領域** は、実際の値 ➊ 示します。 線（期待値）と影になっている部分（実際の値）の比較方法は、異常値があるかどうかを決定します。（観測された値は、[ 異常値検出で使用される統計的手法 ](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) に記載されている高度な統計的手法に基づいて異常と見なされます。）

1. 行の右上隅にある「◥」を選択すると、異常値に関する詳細が表示されます。 これは、実際の値が期待値の上下にどの程度乖離しているかを（パーセントで）示します。

## 折れ線グラフの異常値の表示

折れ線グラフは、異常値を表示できる唯一のビジュアライゼーションです。

折れ線グラフで異常値を表示するには：

1. ビジュアライゼーションヘッダーで ![ 設定 ](/help/assets/icons/Setting.svg) を選択し、オプションのリストで [!UICONTROL **異常値を表示**] オプションが選択されていることを確認します。 詳しくは、[折れ線グラフ](/help/analyze/analysis-workspace/visualizations/line.md)を参照してください。

1. （オプション）信頼区間でグラフを拡大/縮小するには、ビジュアライゼーションヘッダーで ![ 設定 ](/help/assets/icons/Setting.svg) を選択してから、「**[!UICONTROL 異常値で Y 軸のスケールの設定を可能にする]**」オプションを選択します。

   グラフがわかりにくくなる可能性があるので、このオプションは、デフォルトでは選択されていません。

   異常値は、折れ線グラフに次のように表示されます。

   ![ 異常検出された折れ線グラフのビジュアライゼーション ](assets/anomaly-detected-line.gif)

   データの異常値が検出されると、線上に&#x200B;**白い点**&#x200B;が表示されます。（観測された値は、[ 異常値検出で使用される統計的手法 ](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) に記載されている高度な統計的手法に基づいて異常と見なされます。）

   **薄く影になっている部分**&#x200B;は、値が発生するはずの信頼帯または期待範囲です。この期待範囲外の値は、異常値です。

   折れ線グラフに複数の指標がある場合、異常値のみが表示され、その指標の信頼帯を表示するには、各異常値の上にマウスポインターを置く必要があります。

   **点線**&#x200B;は、正確な期待値です。

1. 異常値（白いドット）を選択すると、次の情報が表示されます。

   * 異常値が発生した日付。

   * 異常値の生の値。

   * 期待値を上回るまたは下回る割合の値。これは緑の実線で表されます。

   * 貢献度分析を開始するための **[!UICONTROL 分析]** リンク






