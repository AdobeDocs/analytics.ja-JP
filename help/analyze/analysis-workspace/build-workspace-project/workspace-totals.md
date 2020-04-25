---
description: Workspace の合計の計算方法。
title: Workspace の合計
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Workspace の合計

フリーフォームテーブルでは、合計行が各分類レベルに表示され、2 つの合計を示すことができます。

* **[!UICONTROL Grand Total]** （灰色の「アウトオブ」数） — この合計は、収集されたすべてのヒットを表し、「レポートスイートの合計」とも呼ばれます。 セグメントがパネルレベルまたはフリーフォームテーブル内で適用されると、この合計は、セグメント条件に一致するすべてのヒットを反映するように調整されます。
* **[!UICONTROL Table Total]** （黒い数字）：この合計は、通常、のサブセットまたは等しくなりま [!UICONTROL Grand Total]す。 It reflects any table filters applied within the freeform table, including the [!UICONTROL Include None] option.

![](assets/total-row.png)

## 合計設定を表示

の下に、 **[!UICONTROL Column Settings]**&#x200B;およびのオプションが **[!UICONTROL Show Totals]** ありま **[!UICONTROL Show Grand Total]**&#x200B;す。 これらの設定がオフの場合、合計はテーブルから削除されます。これは、特定の[計算指標のシナリオ](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)などで合計が意味をなさない場合に必要です。

![](assets/column-settings-total.png)

## 静的な行の合計の設定

[静的な行の合計の動作は](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) 、異なります。また、以下で制御されま **[!UICONTROL Row Settings]**&#x200B;す。

* **[!UICONTROL Show sum of current rows as the total]**  — この表の行の合計は、訪問数や訪問者数などの重複を **除外しな** いことを示します。
* **[!UICONTROL Show Grand Total]**  — これは、サーバー側の合計を示します。つまり、合計が訪問数や重複数などの訪問者を除外します。

![](assets/static-rows.png)

## よくある質問

| 質問 | 回答 |
|---|---|
| 灰色の列の割合は、どの「合計」を基準にしていますか。 | これは、次の項目で選択 **[!UICONTROL Percentages]** した設定によって異なりま **[!UICONTROL Row Settings]**&#x200B;す。<ul><li>割合を列ごとに計算 - これがデフォルト設定です。割合は、テーブル合計に基づきます。</li><li>割合を行ごとに計算 - パーセントは総計に基づきます。</li></ul> |
| 設定は合計にどのよ **[!UICONTROL Include Unspecified (None)]** うな影響を与えますか。 | If the **[!UICONTROL Include Unspecified (None)]** setting is unchecked, the None/Unspecified row will be removed from the table, the Table Total, and will carry through to any calculated metrics that use [&#39;Total&#39; metric types](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| フリーフォームテーブルにカスタムテーブルフィルターを適用する場合、そのフィルターに対してすべての計算指標と条件付き書式設定を利用できますか。 | 現在は利用できません。**[!UICONTROL Include Unspecified (None)]** が考慮されますが、カスタム表のフィルターは次の影響を受けません。<ul><li>条件付き書式で使用される列の最大／最小範囲は、すべてのデータを対象とします。</li><li>指標タイプを利用する計 **[!UICONTROL Grand Total]** 算指標です。</li><li>フリーフォームテーブルの行をまたいで計算する関数（例：Column Sum、Column max、Column min、Count、Mean、Median、Percentile、Quartile、Row Count、Standard Deviation、Variance、Cumulative、Cumulative Average、Regression variants、T-Score、T-Test、Z-Score、Z-Test）を使用する計算指標。</li></ul> |
| In Calculated Metrics, what does the **[!UICONTROL Grand Total]** metric type reflect? | **[!UICONTROL Grand Total]** はを引き続き参照し、テ **[!UICONTROL Grand Total]**&#x200B;ーブルまたはに適用されたフィルターは反映されませ **[!UICONTROL Table Total]**&#x200B;ん。 |
| フリーフォームテーブルからデータをコピーして貼り付けるか、CSV でデータをダウンロードすると、合計はどのように表示されますか。 | 合計行には列の設定のみが **[!UICONTROL Table Total]** 反映され、その設定が適用さ **[!UICONTROL Show Totals]** れます。 |

