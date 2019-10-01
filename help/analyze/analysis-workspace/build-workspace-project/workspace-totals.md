---
description: How Workspace totals are calculated.
seo-description: Workspaceの合計の計算方法を説明します。
seo-title: How Workspace totals are calculated.
title: ワークスペースの合計
translation-type: tm+mt
source-git-commit: b2e76715a2bab0931b1ddf8c612c29eea530ce6c

---


# ワークスペースの合計

In Freeform tables, a total row appears at each breakdown level and can show two totals:

* **[!UICONTROL 総合計]** （灰色の「不足」数） — この合計は、収集されたすべてのヒットを表し、「レポートスイートの合計」とも呼ばれます。 When a segment is applied either at the panel level or within the freeform table, this total adjusts to reflect all hits that match the segment criteria.
* **[!UICONTROL Table Total (black number) - this total is typically equal to or a subset of the Grand Total.]**「なしを含む」オプションなど、フリーフォームテーブル内で適用されたすべてのテー [!UICONTROL ブルフィルタ] を反映します。

![](assets/total-row.png)

## Display Total Setting

Under Column Settings, there are options to Show Totals and Show Grand Total. ************&#x200B;これらの設定がオフの場合、合計は表から削除されます。 これは、特定の計算指標のシナリオなどで合計が意味を持たない場合に [必要です](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)。

![](assets/column-settings-total.png)

## 静的行の合計の設定

[静的な行の合計は](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) 、動作が異なり、「行の設定」で制御 **[!UICONTROL されます]**。

* **[!UICONTROL 現在の行の合計を合計として表示]** — 表内の行のクライアント側の合計を表示します。これは、合計が訪問回数や訪問者数などの指標の重複を排 **除しない** ことを意味します。
* **[!UICONTROL 総合計を表示]** — サーバー側の合計を表示します。つまり、合計が訪問回数や訪問者数などの指標の重複を排除します。

![](assets/static-rows.png)

## よくある質問

| 質問 | 回答 |
|---|---|
| 灰色の列の割合の基準はどれか。 | これは、「行の設定」で選択 **[!UICONTROL した]** 「割合」の設定に **[!UICONTROL よって異なります]**。<ul><li>列別にパーセントを計算 — これがデフォルト設定です。 割合は、表の合計に基づきます。</li><li>行別にパーセントを計算 — パーセントは総合計に基づきます。</li></ul> |
| 「未指定（なし）を含 **[!UICONTROL む」設定は、合計にどのように影響しますか]** 。 | 「未指 **[!UICONTROL 定（なし）を含む」設定がオフの場合]** 、「なし/未指定」の行はテーブル（テーブルの合計）から削除され、「合計」の指標タイプを使用する計算指標にも適用さ [れます](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| フリーフォームテーブルにカスタムテーブルフィルターを適用する場合、そのフィルターに対してすべての計算指標と条件付き書式設定を利用できますか。 | 現在はありません。 **[!UICONTROL 「未指定（なし）を含む」は]** 、計上されますが、カスタム表フィルターは次に影響しません。<ul><li>条件付き書式で使用される列の最大/最小範囲は、すべてのデータを対象とします。</li><li>総合計指標タイプを **[!UICONTROL 利用する計算指標]** 。</li><li>フリーフォームテーブルの行全体を計算する関数（列合計、列最大、列最小、数、平均、中央値、百分位、四分位数、行数、標準偏差、偏差、累積平均、回帰、T — スコア、T — スコア、Z — スコア、Z — テストなど）を持つ計算指標。</li></ul> |
| 「計算指標」で、「総合計」指標タ **[!UICONTROL イプは]** 何を反映しますか。 | **[!UICONTROL 総合計は]** 、引き続き総合計 **[!UICONTROL を参照します]**。また、表または表の合計に適用されたフィルタは反 **[!UICONTROL 映されません]**。 |
| フリーフォームテーブルからデータをコピーして貼り付けるか、CSVでデータをダウンロードすると、合計はどのように表示されますか。 | 集計行は、テーブル合計のみを **[!UICONTROL 反映し]** 、列の合計を表示 **[!UICONTROL 設定に従います]** 。 |

