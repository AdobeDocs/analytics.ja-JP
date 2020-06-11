---
title: 分析プラットフォーム間の処理方法とアーキテクチャの違い
description: Adobe Analytics や Google Analytics などの複数のプラットフォーム間で、一部のデータの収集方法と表示方法が異なる場合について説明します。
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 66%

---


# 分析プラットフォーム間の処理方法とアーキテクチャの違い

Adobe Analytics と Google Analytics はどちらも分析ツールですが、データの収集方法と処理方法が大きく異なります。このページでは、特定のディメンションと指標の収集方法に関する主な違いと、同様のレポートで異なる数値が表示される理由について説明します。

## [!UICONTROL バウンス率]

[!UICONTROL バウンス率は、多くの分析ツールでランディングページの効果と関連性を測定するために使用される一般的な KPI です。]これは一般に、Web サイトを訪問したユーザーがランディングページで何も操作せずにそのままサイトから離脱した数を指します。

* In Adobe Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Single-page sessions divided by Sessions**.

どちらのプラットフォームでも、1 回の訪問またはセッションで複数のヒットが送信された場合はバウンスとはみなされません。Adobe Analytics ではカスタムリンクを使用できます。カスタムリンクをクリックしたことによる訪問は、バウンスとはみなされません。Google Analytics は通常、1 つのページで複数のデータリクエストを送信しません。

To achieve better parity between reporting tools, use the [!UICONTROL Single Page Visits] metric in Adobe Analytics instead of [!UICONTROL Bounces] as part of a calculated metric. The [!UICONTROL Single Page Visits] metric includes the total number of visits that only included one-page view, or visits that enter the website but do not include a click to another page.

詳しくは、コンポーネントユーザーガイドの「[バウンス率](/help/components/metrics/bounce-rate.md)」を参照してください。

## [!UICONTROL 訪問回数とセッション数]

[!UICONTROL 訪問回数] （Google Analyticsではセッションと呼ばれます）は、同じユーザーが短時間に行ったページ表示のグループです。 [!UICONTROL どちらのプラットフォームでも、訪問回数は通常、無操作状態が 30 分間続くと期限が切れます。]Both platforms allow customization on when a [!UICONTROL Visit] expires. プラットフォーム間で違いが発生する原因となるシナリオは、複数考えられます。

* **終了日：** Google Analytics のすべてのセッションは、指定された日の午後 11:59 以降に期限が切れます。午前 12:00 以降もユーザーが Web サイトでアクティブな状態のままの場合は、新しいセッションが作成されます。Adobe Analytics では、翌日も続く訪問はすべて同じ訪問として扱います。
* **異なるキャンペーン：** Google Analytics の新しいセッションは、ユーザーのキャンペーンソースが変更されると開始されます。If a new [!UICONTROL Tracking Code] value is seen in Adobe Analytics, it is considered part of the same visit.
* **手動によるセッションの上書き：** Google Analytics では、`sessionControl` を使用してセッションを手動で開始または終了すると、新しいセッションが開始されます。[!UICONTROL Adobe Analytics では、訪問を手動で終了することはできません。]
* **Adobe Analyticsでの外れ値の訪問検出：** Adobe Analyticsの新しい [!UICONTROL 訪問] ：連続アクティビティが12時間続いた場合、2,500ヒットまたは100ヒットに達した場合、100秒以内に開始が自動的に発生します。 これらの各検出条件は通常、ボットアクティビティによってトリガーされます。

詳しくは、コンポーネントユーザーガイドの「[訪問回数指標](/help/components/metrics/visits.md)」を参照してください。
