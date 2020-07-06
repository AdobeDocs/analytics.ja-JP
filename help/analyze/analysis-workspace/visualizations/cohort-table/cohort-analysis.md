---
title: コホート分析とは
description: Analysis Workspaceでのコホートの分析について説明します。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 46%

---


# What is [!UICONTROL Cohort Analysis]?

*`cohort`* とは、特定の期間、共通の特性を共有する人々のグループのことです。[!UICONTROL コホート分析は、例えば、コホートがブランドとどのように関わっているかを学ぶ場合に便利です。]トレンドの変更を簡単に見分けて、それに応じて対応できます(Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

コホートレポートを作成したら、コンポーネント（特定のディメンション、指標およびセグメント）をキュレーションして、任意のユーザーとコホートレポートを共有できます。詳しくは、[キュレーションおよび共有](/help/analyze/analysis-workspace/curate-share/curate.md)を参照してください。

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* 目的のアクションを促進するために設計したキャンペーンを開始する。
* 顧客のライフサイクルのまさに適切なタイミングでマーケティング予算を振り替える。
* 価値を最大限にするために、試用やオファーを終了するタイミングを認識する。
* 価格やアップグレードパスなどの領域で、A/B テストの着想を得る。
* View a [!UICONTROL Cohort Analysis] report within a Guided Analysis report.

[!UICONTROL コホート分析] は、 [!UICONTROL Analysis Workspaceへのアクセス権を持つアドビのAnalyticsのすべてのお客様が利用できます]。

[コホート分析（YouTube）](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)（4:36）

>[!IMPORTANT]
>
>[!UICONTROL コホート分析]
>
>は、セグメント化不可能な指標（計算指標を含む）、整数以外の指標（売上高など）、回数をサポートしていません。 セグメントで使用できる指標のみが
>[!UICONTROL コホート分析]。一度に1つ増やすことしかできません。

## コホート分析の機能

次の機能を使用すると、作成するコホートを細かく制御できます。

### [!UICONTROL リテンションテーブル]

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. 指標は最大 3 個、セグメントは最大 10 個含めることができます。

![](assets/retention-report.png)

### [!UICONTROL チャーンテーブル]

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. 指標は最大 3 個、セグメントは最大 10 個含めることができます。

![](assets/churn-report.png)

### [!UICONTROL ローリング計算]

「含む」列ではなく、直前の列に基づいてリテンションまたはチャーンを計算できます。

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL 待ち時間テーブル]

インクルージョンイベントが発生した前後の経過時間を測定します。このツールは、イベント発生前後の分析に役立ちます。The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL カスタムディメンションコホート]

デフォルトの時間に基づくコホートではなく、選択したディメンションに基づいてコホートを作成します。Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

コホートレポートを設定および実行する方法については、コホート分析レポートの [設定を参照してください](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

