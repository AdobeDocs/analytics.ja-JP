---
description: 対象者にとって最も有用になるようにグラフをカスタマイズする手順を説明します。
title: レポートのグラフの変更
topic: Reports and analytics
uuid: c2e81c6c-bfe9-4457-8b5d-512255ca9711
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# レポートのグラフの変更

対象者にとって最も有用になるようにグラフをカスタマイズする手順を説明します。

使用できるグラフの種類は、実行するレポートの種類によって異なります。例えば、トレンドレポートではトレンドライングラフが使用されますが、トレンドラインに加えて縦棒グラフを使用することで日単位、週単位、月単位のトレンドを明確に示すことができます。また、閲覧されたページの割合を円グラフを使用して表示することもできます。

**レポートグラフを変更するには**

1. レポートを実行します。
1. クリック **[!UICONTROL Configure Graph]**.
1.  グラフタイプを選択します。

   **[!UICONTROL Trend Line]**:トレンドラインは、レポート指標の日別トレンドを示し、1つの指標の経時的なトレンドを示します。

   ![](assets/graph_trend_line.png)

   **[!UICONTROL Smooth Line]**:このグラフタイプは、で使用しま [!UICONTROL Video Detail Report]す。 ビデオの指定セグメントの閲覧回数または閲覧率示します。ビデオの特定セグメントの視聴回数が増加している場合、視聴者がビデオのその部分を巻き戻して複数回視聴していることを示しています。閲覧率を使用した場合、グラフに示された率は閲覧された全セグメントに対する割合を示します。そのセグメントを閲覧した訪問者の割合ではありません。例えば、グラフにすべてのレポートセグメントの合計視聴回数が 39 回と表示されているとします。0 ～ 10 秒のセグメントの視聴回数が 10 回である場合、このセグメントが視聴された割合は約 26 パーセントとなります。

   ![](assets/graph_smooth_line.png)

   **[!UICONTROL Area]**:面グラフはトレンドライングラフに似ていますが、線より下の部分が塗りつぶされます。 面グラフを表示するには、トレンドレポートでなければなりません。

   ![](assets/graph_area.png)

   **[!UICONTROL Stacked Area]**:積み重ね面グラフは、複数の製品やキャンペーンの経時的なトレンドを示す場合に便利です。 例えば、トップ 5 の製品の売上を示すトレンドを表示すると、一定期間内にこれらの製品がもたらす総売上高を一目で見ることができます。検索フィルターを使って特定の製品を含めたり除外すると、この表示のデータをさらに絞り込むことができます。

   ![](assets/graph_stacked_area.png)

   **[!UICONTROL Vertical Bar]**:縦棒グラフでは、レポート指標の相対的割合が表示されます。

   ![](assets/graph_vertical_bars.png)

   **[!UICONTROL Stacked Vertical Bar]**:同様の項目を積み重ねることで、項目の全体的な影響を表示的に把握できます。 For example, in a [!UICONTROL Campaign Report], you can stack similar success metrics and see which campaign is generating the most total success. 積み重ねることにより、個々の指標ではあまり実績がよくなくても、複数の指標を組み合わせて総合すると実績が最高となるキャンペーンが一目でわかるようになります。

   ![](assets/graph_stacked_vertical.png)

   **[!UICONTROL Horizontal Bar]**:横棒グラフは縦棒グラフに似ていますが、列が水平に表示されます。

   ![](assets/graph_horizontal_bar.png)

   **[!UICONTROL Stacked Horizontal Bar]**:積み重ね横棒グラフは縦棒グラフに似ていますが、列が水平に表示されます。

   ![](assets/graph_stacked_horizontal.png)

   **[!UICONTROL Pie]**:円グラフでは、相対的に高い割合の指標値、および選択した指標の割合が全体を基準にして表示されます。 円グラフは、ランクレポートで表示できます。

   ![](assets/graph_pie.png)

   **[!UICONTROL Scatter]**:散布グラフでは、選択指標の相対的なデータが散布図で表示されます。 散布グラフではデータを 2 次元表示できるので、異常値を識別できます。

   ![](assets/graph_scatter.png)

   **[!UICONTROL Bubble]**:バブルグラフでは、選択指標の相対的なデータがバブルで表示されます。 バブルの位置により横軸と縦軸のそれぞれの指標間の関係が、バブルのサイズによりメインレポート指標が表されます。バブルグラフではデータを 2 次元表示できるので、異常値を識別できます。

   ![](assets/graph_bubble.png)

