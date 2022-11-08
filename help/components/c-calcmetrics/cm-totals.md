---
title: 計算指標の合計
description: Analytics ツールにおいて計算指標の合計がどのように異なるかを説明します。
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 97%

---

# 計算指標の合計

計算指標の合計の表示方法は、[!DNL Reports & Analytics] と [!DNL Analysis Workspace] では異なります。ここでは、相違点について説明します。

## [!DNL Reports & Analytics] での計算指標の合計

[!DNL Reports & Analytics] でレポートを表示すると、合計の下に常に計算指標が `n/a` と表示されます。すべての計算指標はユーザー定義なので、多くの場合、この合計は意味をなしません。次の例をご覧ください。

サイトで何かを購入した訪問のパーセンテージを判断するために、組織が計算指標「`orders`/`visits`」を作成した。この指標を製品レポートに組み込むと、複数の製品が 1 件の注文に関連付けられます。また、複数の製品が 1 回の訪問に関連付けられます。計算指標の合計がこのレポートに含まれると、次の質問が発生します。

| 質問 | 回答 |
|---|---|
| 行項目を合計することに意味はありますか。 | 1 回の注文に複数の製品を含めたり、1 回の訪問に複数の製品を含めたりできるので、意味はありません。行項目を集計した場合、注文の合計と合計訪問回数は、実際の注文の合計と合計訪問回数と一致しません。 |
| 合計注文件数と合計訪問回数の両方を取得することには意味がありますか。 | 合計は個々の行項目の合計と一致しないので、両方を取得しても意味はありません。さらに、合計注文件数と合計訪問回数は別々に計算されます。 |

計算指標がレポートで意味を持つかどうかを判断する論理的かつ具体的な方法がないので、指標の合計は完全に省略されます。総計を取得するには、次のいずれかを実行できます。

* 計算指標（含める指標の合計バージョンを含む）を作成します。
* スケジュール可能なデータ抽出レポートを作成します。
* [!DNL ReportBuilder] 内でデータリクエストを作成します。
* [!DNL Analysis Workspace] を使用します（以下を参照）。

## [!DNL Analysis Workspace] での計算指標の合計

Analysis Workspace でデータを表示すると、ほとんどの場合、計算指標の合計が表示されます。レポートの行の形式（小数や通貨など）が混在している場合など、合計を指定できないことがあります。

合計が表示されている場合は多くの場合、サーバー側で計算され、訪問回数や訪問者数などの指標の重複を排除します。状況によっては、テーブルの行全体を合計して、クライアント側で計算指標が生成されることがあります。つまり、合計では、訪問回数や訪問者数などの指標の重複が排除されません。これは次のように発生します。

* フリーフォームテーブルで、[静的な行](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)が使用され、「**[!UICONTROL 現在の行の合計として表示]**」オプション（デフォルト）が選択されている場合。
* [ドーナツビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/donut.md)では、数値の合計は 100％になります。

Analysis Workspace での合計の詳細については、[Workspace の合計](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html#static-row-total)を参照してください。
