---
description: 既存の指標から作成できる計算指標について説明します。
keywords: 計算指標
title: 計算指標の概要
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
TQID: https://experienceleague.adobe.com/3bZdi3MZ8Q5MibUfwOlO1CmumXTqlWxBH6hy35M9tUk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 317
ht-degree: 75%

---

# 計算指標の概要

計算指標は、既存の指標から作成できるカスタム指標です。

計算指標は、既存の指標から作成できるカスタム指標です。 計算指標では、実装を変更せずにデータを分析できるカスタム指標の作成、管理およびキュレーションを行う柔軟な方法を提供します。

計算指標は各[!DNL Analytics] パッケージで利用できますが、Adobe Analytics Foundation Pack for CX Enterpriseでは、[形式の種類（小数点、時間、パーセント、通貨） &#x200B;](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)、[配分の変更（デフォルト、線形、パーティシペーションなど） &#x200B;](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)、[指標の種類（標準、合計） &#x200B;](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)、[基本演算子](workflow/c-build-metrics/cm-build-metrics.md#operators) （加算、減算、乗算、除算）などの基本的な計算指標に限定されています。


詳しくは、[Adobe Analytics 製品の説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-analytics.html)を参照してください。

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/calculated-metrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## 機能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

次のことが可能です。

* [!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 異常値検出]、[!UICONTROL 貢献度分析]をまたいで[指標を作成](/help/components/calculated-metrics/workflow/cm-workflow.md)する。
* 実装を変更せずに、レポート実行時に導出される[セグメント化された指標を作成](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)する。 例えば、初回のセッションの訪問者の数を含む、*初回訪問者数*&#x200B;の指標を作成できます。

* レポートスイート間で[指標を共有](/help/components/calculated-metrics/workflow/cm-sharing.md)する。 つまり、新しく作成されたすべての指標は、同じログイン会社のすべてのレポートスイートに適用されます。

* データをわかりやすく記述するための[統計関数を組み込む](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)。 例えば、レポート内の項目数をカウントしたり、各項目の標準偏差の数を追加したりできます。

## 制限事項

一部の [!DNL Analytics] 機能では、計算指標を使用できません。

* [!UICONTROL Analysis Workspace &#x200B;]&#x200B;[!UICONTROL のフォールアウト]
* [!UICONTROL Analysis Workspace のコホート分析]
* [!UICONTROL Data Warehouse]
* [!UICONTROL セグメント]
* [!DNL Analytics] for [!DNL Target]


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [計算指標](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [セグメントのセグメント化計算指標](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[指標の作成](/help/components/calculated-metrics/workflow/cm-workflow.md)
>[指標の構築](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)
>[関数の使用](/help/components/calculated-metrics/workflow/c-build-metrics/cm-using-functions.md)
>
