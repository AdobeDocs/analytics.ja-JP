---
description: 計算指標および高度な計算指標は、既存の指標から作成できるカスタム指標です。
keywords: 計算指標;高度な計算指標
title: 計算指標および高度な計算指標
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 9714863374052e257e1d6349c442fc74182a0a2f
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 100%

---

# 計算指標および高度な計算指標

計算指標および高度な計算指標は、既存の指標から作成できるカスタム指標です。

計算指標ツールを使用すると、指標を極めて柔軟に作成および管理できます。マーケター、製品マネージャーおよびアナリストは、[!DNL Analytics] の実装を変更することなくデータを照会できます。各 [!DNL Analytics] パッケージで利用可能なカスタム指標を次に示します。

* Adobe [!DNL Analytics] Foundation：計算指標
* [Adobe Analytics Select](https://www.adobe.com/jp/data-analytics-cloud/analytics/select.html)：計算指標 + 高度な計算指標
* [Adobe Analytics Prime](https://www.adobe.com/jp/data-analytics-cloud/analytics/prime.html)：計算指標 + 高度な計算指標
* [Adobe Analytics Ultimate](https://www.adobe.com/jp/data-analytics-cloud/analytics/ultimate.html)：計算指標 + 高度な計算指標

次に、計算指標と高度な計算指標の機能比較を示します。

| ビルダーのオプション | 計算指標 | 高度な計算指標 |
|---|---|---|
| [形式のタイプ（小数、時間、割合、通貨）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | ○ | ○ |
| [アトリビューションの変更（デフォルト、線形、パーティシペーションなど）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | ○ | ○ |
| [指標のタイプ（標準、合計）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | ○ | ○ |
| 基本的な演算子（可算、減算、乗算、除算） | ○ | ○ |
| [セグメントの適用](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | × | ○ |
| [基本的な関数（カウント、絶対値、平均など）](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | × | ○ |
| [高度な関数（回帰、if/then、t スコアなど）](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | × | ○ |

## 機能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

次のことが可能です。

* [!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 異常値検出]、[!UICONTROL 貢献度分析]をまたいで指標を作成します。
* 実装を変更せずに、レポート実行時に導出されるセグメント化された指標を作成します。これらの指標はセグメントに基づいているので、時系列で表示できます。

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [計算指標](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

* レポートスイート間で指標を共有する。つまり、新しく作成されたすべての指標は、同じログイン会社のすべてのレポートスイートに適用されます。
* （高度な計算指標のみ）指標のセグメント。例えば、初回セッションの訪問者数を含む、「初回訪問者数」の指標を作成できます。

* （高度な計算指標のみ）データをわかりやすく記述するための統計関数を組み込む。例えば、レポート内の項目数をカウントしたり、各項目の標準偏差の数を追加したりできます。


## 制限事項

一部の [!DNL Analytics] の機能では、イベントは使用できますが、計算指標は使用できません。

* [!UICONTROL Analysis Workspace ][!UICONTROL のフォールアウト]
* [!UICONTROL Analysis Workspace のコホート分析]
* [!UICONTROL Data Warehouse]
* [!UICONTROL セグメント]
* [!DNL Analytics] for [!DNL Target]


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [計算指標](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [セグメントのセグメント化計算指標](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->