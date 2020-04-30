---
description: ヒストグラムは、Analysis Workspace の新しいビジュアライゼーションタイプです。
title: ヒストグラム
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# ヒストグラム

ヒストグラムは、棒グラフに似ていますが、数を範囲（グループ）でグループ化します。Analytics は、数から範囲への「グループ化」を自動化しますが、[詳細設定](#section_09D774C584864D4CA6B5672DC2927477)で設定を変更できます。

## ヒストグラムのビルド {#section_74647707CC984A1CB6D3097F43A30B45}

ヒストグラムを作成するには

1. Click **[!UICONTROL Visualizations]** in the left rail.
1. Drag **[!UICONTROL Histogram]** to the panel.
1. Choose a Metric to drag to the Histogram visualization and click **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE]ヒストグラムは、計算指標ではなく、標準指標のみをサポートします。

ここでは、実訪問者数ごとにページビュー数指標を使用しました。最初の（左の）グループは、実訪問者数ごとの 1 ページビューに対応し、2 番目のグループは 2 ページビューに対応します（以下同様）。

![](assets/histogram2.png)

## 詳細設定 {#section_09D774C584864D4CA6B5672DC2927477}

ヒストグラム設定を調整するには、右上隅の設定（「ギア」）アイコンをクリックします。変更できる設定を次に示します。

| ヒストグラムの設定 | 説明 |
|---|---|
| 開始グループ | どのグループからヒストグラムが始まるかを決定します。1 がデフォルトです。開始の数を 0 から無限大まで（負の数はなし）設定できます。 |
| 指標グループ | データ範囲（グループ）の数を増減できます。グループの最大数は 50 です。 |
| 指標グループのサイズ | 各グループのサイズを設定できます。例えば、グループサイズを 1 ページビューから 2 ページビューに変更できます。 |
| カウント方法 | Lets you choose among [Visitor](/help/components/c-variables/c-metrics/visitors.md), [Visit](/help/components/c-variables/c-metrics/metrics-visit.md), or [Hit Type](/help/components/c-variables/dimensionslist/report-hit-type.md). 例えば、訪問ごとのページビュー、訪問者ごとのページビュー、ヒットごとのページビューです。ヒットの場合、フリーフォームテーブルの y 軸指標として、「回数」が使用されます。 |

<!--Russ or Meike - Check Hit Type link above. -->

**例**：

* 開始グループ：1、指標グループ：5、指標グループのサイズ：2 は、1～2、3～4、5～6、7～8、9～10 というヒストグラムになります。
* 開始グループ：0、指標グループ：3、指標グループのサイズ：5 は、0～4、5～9、10～14 というヒストグラムになります。

## ヒストグラムデータの表示と編集 {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

To view or change the data source for the histogram chart, click the dot next to the Histogram header to go to **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

テーブルに表示される事前に作成されたセグメントは、内部セグメントで、セグメントセレクターには表示されません。Click the &quot;i&quot; icon next to the segment name, then click **[!UICONTROL Make public]** to make the segment public.

![](assets/prebuilt_segments.png)

データを分類するなど、フリーフォームデータテーブルおよびその他のビジュアライゼーションを管理するその他の方法を確認するには、[こちら](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)を参照してください。
