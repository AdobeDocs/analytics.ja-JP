---
title: コホート分析の概要と仕組み
description: オーディエンスに関するデータをより深く掘り下げ、コホート分析を使用して関連グループに分類します。 Analysis Workspace のコホート分析について説明します。
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 33%

---

# コホートテーブルの概要 {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="コホートテーブル"
>abstract="コホートビジュアライゼーションを作成して、イベントの完了に基づいてユーザーをグループ化し、進行中のエンゲージメントと時間の経過に伴うチャーンを分析します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="コホートテーブル"
>abstract="イベントの完了に基づいてユーザーをグループ化し、進行中のエンゲージメントとチャーンの推移を分析します。<br/><br/>**パラメーター&#x200B;**<br/>**インクルージョン条件**：最初の訪問者コホートの定義に使用するコンポーネント。<br/>**再来訪条件**：訪問者が再来訪したかどうかを判断するために使用するコンポーネント。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_この記事は、![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)_**Adobe Analytics_ のコホートテーブルに関する説明です**。_<br/>_この記事の [CustomerJourneyAnalytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis)_ _**Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) バージョンについては、![ コホートテーブル** を参照してください。_

>[!ENDSHADEBOX]



*コホート* とは、特定の期間、共通の特徴を共有する人々のグループです。 ![ テキスト番号付き ](/help/assets/icons/TextNumbered.svg)**[!UICONTROL コホートテーブル]** ビジュアライゼーションは、例えば、コホートがブランドとどのように関わっているかを学びたい場合に役立ちます。 トレンドの変更を簡単に見分けて、それに応じて対応できます（[!UICONTROL コホート分析]の説明は、[コホート分析 101](https://ja.wikipedia.org/wiki/Cohort_analysis) など、Web 上で参照できます）。

コホートレポートを作成したら、コンポーネント（特定のディメンション、指標およびフィルター）をキュレートして、任意のユーザーとコホートレポートを共有できます。[キュレートおよび共有](/help/analyze/analysis-workspace/curate-share/curate.md)を参照してください。

[!UICONTROL  コホートテーブル ] を使用して実行できる操作の例：

* 目的のアクションを促進するために設計したキャンペーンを開始する。
* 顧客のライフサイクルのまさに適切なタイミングでマーケティング予算を振り替える。
* 価値を最大化するために、体験版またはオファーを終了するタイミングを認識します。
* 価格やアップグレードパスなどの領域で、A/B テストの着想を得る。

[!UICONTROL  コホートテーブル ] は、[!UICONTROL Analysis Workspace] へのアクセス権を持つすべてのCustomer Journey Analyticsユーザーが利用できます。


>[!BEGINSHADEBOX]

デモビデオについては、![Analysis Workspaceでの VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ コホート分析 ](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL  コホート分析 ] では、フィルタリングできない指標（計算指標など）、整数以外の指標（売上高など）、発生件数はサポートしていません。 [!UICONTROL  コホート分析 ] で使用できるのはフィルターで使用できる指標のみで、一度に増やせるのは 1 つのみです。

Customer Journey Analyticsのコホートテーブルでは、ダブルベース（または任意の数値ベース）の指標をサポートしています。 例えば、Purchase.Value （double）はインクルージョン/リターン指標として使用できます。 また、Analytics Source Connector を介してAdobe Experience Platformに渡されるすべての指標も重複しています。

## コホートテーブル機能

以下の節では、作成するコホートを微調整して制御できるコホート分析機能について説明します。

コホートの作成および [!UICONTROL  コホート分析 ] レポートの実行について詳しくは、[ コホートテーブルの設定 ](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md) を参照してください。

### [!UICONTROL  リテンション ] テーブル

[!UICONTROL  保持 ] コホートテーブルは人物を返します。各データセルは、その期間中にアクションを実行したコホート内の人物の生の数と割合を示します。 指標は最大 3 個、フィルターは最大 10 個含めることができます。

![ コホート内のユーザーの単位と割合を示すレンションコホートレポート。](assets/retention-report.png)

### [!UICONTROL  チャーン ] テーブル

[!UICONTROL  チャーン ] コホートテーブルは、リテンション テーブルの逆であり、コホートの返品条件を満たさなかったユーザーまたは満たさなかったユーザーの経時的な数を示します。 指標は最大 3 個、フィルターは最大 10 個含めることができます。

![ コホートの返品条件を満たさないユーザーの数量と割合を示すチャーンテーブル。](assets/churn-report.png)

### [!UICONTROL ローリング計算]

リテンションまたはチャーンは、「ローリング計算」と呼ばれる「含める」列ではなく、前の列に基づいて計算できます。

![ 前のデータ列に基づく計算を示すコホート保持レポート。](assets/retention-report-rolling.png)

### [!UICONTROL  待ち時間 ] テーブル

待ち時間テーブルは、インクルージョンイベントが発生する前後の経過時間を測定します。 待ち時間の測定は、事前分析および事後分析に最適なツールです。 「**[!UICONTROL 含む]**」列がテーブルの中央にあり、インクルージョンイベント発生の前と後の期間が両側に表示されます。

![ イベント前後の経過時間を示すコホートレポート。](assets/retention-report-latency.png)

### [!UICONTROL  カスタムディメンション ] コホート

時間ベースのコホート（デフォルト）ではなく、選択したディメンションに基づいてコホートを作成できます。 [!UICONTROL  市区町村地域 ]、[!UICONTROL  マーケティングチャネル ]、[!UICONTROL  キャンペーン ]、[!UICONTROL  製品 ]、[!UICONTROL  ページ ]、[!UICONTROL  地域 ] などのディメンションや、その他のディメンションを使用して、リテンションがどのように変化しているかを表示します。 これらのディメンションの様々な値に基づいています。

![ 選択したディメンションでカスタマイズされたレポートを表示するコホートレポート。デフォルトの時間ベースのコホートではありません。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[ コホートテーブルの設定 ](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>



<!--
A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and segments), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer, in order to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort Analysis] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://video.tv.adobe.com/v/25965?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-segmentable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. 
>
>Only metrics that can be used in segments can be used in [!UICONTROL Cohort Analysis], and they can only be incremented by >1 at a time. 

## Cohort Analysis capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort Analysis report](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention] Table

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 segments.

![](assets/retention-report.png)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://video.tv.adobe.com/v/25962?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://video.tv.adobe.com/v/25966?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


### [!UICONTROL Rolling Calculation]

Lets you calculate retention or churn based on the previous column, not the included column.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Table

Measures the time that has elapsed before and after the inclusion event occurred. This is an excellent tool for pre/post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Create cohorts based on a selected dimension, and not time-based cohorts, which are the default. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

-->
