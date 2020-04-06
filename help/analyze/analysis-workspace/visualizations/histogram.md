---
description: ヒストグラムは、Histogram Workspaceの新しいビジュアライゼーション分析です。
title: ヒストグラム
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# ヒストグラム

ヒストグラムは棒グラフに似ていますが、数値を範囲（グループ）にグループ化します。 Analyticsは、数値の範囲への「グループ化」を自動化しますが、詳細設定で設定を変更 [できます](#section_09D774C584864D4CA6B5672DC2927477)。

## ヒストグラムのビルド {#section_74647707CC984A1CB6D3097F43A30B45}

ヒストグラムを作成するには

1. Click **[!UICONTROL Visualizations]** in the left rail.
1. Drag **[!UICONTROL Histogram]** to the panel.
1. Choose a Metric to drag to the Histogram visualization and click **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE]ヒストグラムは、計算指標ではなく、標準指標のみをサポートします。

ここでは、個別訪問者ごとのページ表示指標を使用しました。 最初の（左の）グループは、一意の訪問者ごとに1ページの表示に対応し、2番目のグループは2ページの表示に対応します。

![](assets/histogram2.png)

## 詳細設定 {#section_09D774C584864D4CA6B5672DC2927477}

ヒストグラムの設定を調整するには、右上隅の設定（「歯車」）アイコンをクリックします。 次の設定を変更できます。

| ヒストグラム設定 | 機能 |
|---|---|
| 開始グループ | ヒストグラムのどのグループに開始を入れるか。 &quot;1&quot;がデフォルトです。 開始数は0から無限大（負の数はなし）の範囲で設定できます。 |
| 指標グループ | データ範囲（グループ）の数を増減できます。グループの最大数は50です。 |
| 指標グループのサイズ | 各グループのサイズを設定できます。 例えば、グループサイズを1ページ表示から2ページ表示に変更できます。 |
| カウント方法 | 「 [訪問者](https://marketing.adobe.com/resources/help/ja_JP/reference/visitors.html)」、「訪問 [」](https://marketing.adobe.com/resources/help/ja_JP/reference/metrics_visit.html)、「ヒッ [ト」から選択](https://marketing.adobe.com/resources/help/ja_JP/reference/hit.html)します。 例えば、1回の訪問あたりのページ表示数、1回の訪問者あたりのページ表示数、1回のヒットあたりのページ表示数などです。 ヒットの場合、フリーフォームテーブルの y 軸指標として、「回数」が使用されます。 |

**例**：

* 開始グループ：1;指標グループ：5;指標グループのサイズ：2を指定すると、次のヒストグラムが作成されます。1-2、3-4、5-6、7-8、9-10。
* 開始グループ：0;指標グループ：3;指標グループのサイズ：5を指定すると、次のヒストグラムが作成されます。0-4、5-9、10-14

## ヒストグラムデータの表示と編集 {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

To view or change the data source for the histogram chart, click the dot next to the Histogram header to go to **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

テーブルに表示される事前に作成されたセグメントは、内部セグメントで、セグメントセレクターには表示されません。Click the &quot;i&quot; icon next to the segment name, then click **[!UICONTROL Make public]** to make the segment public.

![](assets/prebuilt_segments.png)

データを分類するなど、フリーフォームデータテーブルおよびその他のビジュアライゼーションを管理するその他の方法を確認するには、[こちら](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/freeform-analysis-visualizations.html)を参照してください。
