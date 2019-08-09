---
title: 計算指標の合計
seo-title: 計算指標の合計
description: Analyticsツールで計算指標の合計がどのように異なるかを知る
seo-description: 計算指標の合計の計算方法
translation-type: tm+mt
source-git-commit: 774975605de502b66279888d8dd8ef58989a40de

---


# 計算指標の合計

計算指標の合計の表示方法は [、DNL Reports&amp; Analytics] と [DNL Analysis Workspaceによって]異なります。ここでは、相違点について説明します。

## 計算指標の合計 [!DNL Reports & Analytics]

で [!DNL Reports & Analytics]レポートを表示すると、計算指標は常に合計の下に表示 `n/a` されます。すべての計算指標はユーザー定義であるため、この合計は意味がありません。次の例をご覧ください。

貴社では、サイト上で何かを購入した訪問のパーセントを判断するために、計算指標 [の注文] 件数/ [訪問回数] を作成しました。この指標を製品レポートに取り込んだ場合、複数の製品が単一の注文に関連付けられます。また、複数の製品が1回の訪問に関連付けられています。このレポートに計算指標の合計が含まれている場合、次の質問が発生します。

| 質問 | 回答 |
|---|---|
| 行項目を合計すると意味がありますか。 | 複数の製品を単一の注文に含めることができるため、1回の訪問に複数の製品を含めることはできません。行項目が集計された場合、合計注文回数と合計訪問回数は実際の合計注文件数と合計訪問回数と一致しません。 |
| 合計注文数と合計訪問回数は、次のようになります。 | 合計が個々の行項目の合計と一致しないため、一致しません。さらに、合計注文件数と合計訪問回数は個別に計算指標として計算されます。 |

計算指標がレポートで意味を持つかどうかを判断する論理的および具象的な方法はないので、指標の合計は完全に省略されます。総合的な合計を取得する場合は、次のいずれかを実行できます。

* 含める指標の合計バージョンを含む計算指標を作成します。
* データ抽出レポートを作成して、スケジュールを設定できます。
* ReportBuilder内でデータリクエストを作成します。
* Analysis Workspaceを使用します（以下を参照）。

## 計算指標の合計 [!DNL Analysis Workspace]

Analysis Workspaceでは、状況によって、計算指標が合計され、合計が表示されます。

* [静的行](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) と [!UICONTROL 、現在各列] オプション（デフォルト）にある値を合計することで、合計を計算します。
* [ドーナツグラフのビジュアライゼーションで](/help/analyze/analysis-workspace/visualizations/donut.md)、
* 変更 [の概要ビジュアライゼーションで](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)、
