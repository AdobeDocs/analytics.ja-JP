---
title: コホートテーブルの概要
description: コホート分析を使用して、オーディエンスに関するデータをより深く掘り下げ、そのデータを関連するグループに分割する方法を説明します。 Analysis Workspaceでのコホート分析の使用。
feature: Visualizations
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 90%

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

_この記事では、_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** のコホートテーブルについて説明します。_<br/>_この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** バージョンについて詳しくは、[コホートテーブル](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis)を参照してください。_

>[!ENDSHADEBOX]



*コホート*&#x200B;は、特定の期間にわたって共通の特性を持つ人物のグループです。![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL コホートテーブル]**&#x200B;ビジュアライゼーションは、例えば、あるコホートが、あるブランドとどのようにエンゲージしているかを知るのに役立ちます。トレンドの変更を簡単に見分けて、それに応じて対応できます（[!UICONTROL コホート分析]の説明は、[コホート分析 101](https://ja.wikipedia.org/wiki/Cohort_analysis) など、Web 上で参照できます）。

コホートレポートを作成したら、コンポーネント（特定のディメンション、指標およびフィルター）をキュレートして、任意のユーザーとコホートレポートを共有できます。[キュレートと共有](/help/analyze/analysis-workspace/curate-share/curate.md)を参照してください。

[!UICONTROL コホートテーブル]で実行できる操作の例：

* 目的のアクションを促進するために設計したキャンペーンを開始する。
* 顧客のライフサイクルのまさに適切なタイミングでマーケティング予算を振り替える。
* 価値を最大化するために、体験版やオファーを終了するタイミングを認識する。
* 価格やアップグレードパスなどの領域で、A/B テストの着想を得る。

[!UICONTROL &#x200B; コホートテーブル &#x200B;] は、[!UICONTROL Analysis Workspace] へのアクセス権を持つすべてのAdobe Analytics ユーザーが利用できます。


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace のコホート分析](https://video.tv.adobe.com/v/3430080/?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL コホート分析]は、フィルタリングできない指標（計算指標を含む）、整数以外の指標（売上高など）、発生件数をサポートしていません。[!UICONTROL コホート分析]で使用できるのはフィルターで使用できる指標のみで、一度に 1 つのみを増分できます。

Adobe Analyticsのコホートテーブルでは、ダブルベース（または任意の数値ベース）の指標をサポートしています。 例えば、Purchase.Value（2 倍）はインクルージョン／リターン指標として使用できます。また、Analytics ソースコネクタ経由で Adobe Experience Platform に渡されるすべての指標も 2 倍になります。

## コホートテーブルの機能

次の節では、作成しているコホートを微調整して制御できるコホート分析機能について説明します。

コホートの作成と[!UICONTROL コホート分析]レポートの実行について詳しくは、[コホートテーブルの設定](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)を参照してください。

### 保持テーブル

[!UICONTROL リテンション]コホートテーブルはユーザーを返します。各データセルには、その期間中にアクションを実行したコホートのユーザーの生の数と割合が表示されます。指標は最大 3 個、フィルターは最大 10 個含めることができます。

![コホート内のユーザーの単位と割合を示すリテンションコホートレポート。](assets/retention-report.png)

### チャーンテーブル

[!UICONTROL チャーン]コホートテーブルは、リテンションテーブルの逆で、時間の経過と共にコホートからフォールアウトしたユーザーや、コホートへのリターン条件を満たさなかったユーザーが表示されます。指標は最大 3 個、フィルターは最大 10 個含めることができます。

![コホートのリターン条件を満たさなかった人物の数と割合を示すチャーンテーブル。](assets/churn-report.png)

### ローリング計算

リテンションまたはチャーンは、「含む」列ではなく、前の列に基づいて計算できます。これをローリング計算と呼びます。

![前のデータ列に基づく計算を示すコホートリテンションレポート。](assets/retention-report-rolling.png)

### 待ち時間表

待ち時間テーブルは、インクルージョンイベント発生前後の経過時間を測定します。待ち時間の測定は、前後の分析に最適なツールです。「**[!UICONTROL 含む]**」列がテーブルの中央にあり、インクルージョンイベント発生の前と後の期間が両側に表示されます。

![イベント前後の経過時間を示すコホートレポート。](assets/retention-report-latency.png)

### カスタムディメンションコホート

時間ベースのコホート（デフォルト）ではなく、選択したディメンションに基づいてコホートを作成できます。[!UICONTROL 市区町村地域]、[!UICONTROL マーケティングチャネル]、[!UICONTROL キャンペーン]、[!UICONTROL 製品]、[!UICONTROL ページ]、[!UICONTROL 地域]などのディメンションや、その他のディメンションを使用して、リテンションがどのように変化しているかを表示します。これらのディメンションの様々な値に基づいています。

![デフォルトの時間ベースのコホートではなく、選択したディメンションを使用してカスタマイズされたレポートを示すコホートレポート。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[コホートテーブルの設定](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
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

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://video.tv.adobe.com/v/3430084?quality=12&learn=on&captions=jpn){target="_blank"} for a demo video.

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

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://video.tv.adobe.com/v/3430172?quality=12&learn=on&captions=jpn){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://video.tv.adobe.com/v/3430158?quality=12&learn=on&captions=jpn){target="_blank"} for a demo video.

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
