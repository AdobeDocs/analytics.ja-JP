---
description: 概要番号および変更ビジュアライゼーションを使用して、プロジェクト内の重要なデータポイントを表示します。
title: 数の概要と変更の概要
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 93%

---

# [!UICONTROL 数値概要] と [!UICONTROL 変更概要]

*この記事は、**Adobe Analyticsの数値概要と変更概要のビジュアライゼーションについて説明します**。<br/> この記事の [3}Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change) バージョンについては、**数値の概要と変更の概要* を参照してください。**

以下は、これら 2 つのビジュアライゼーションに関するビデオです。

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## [!UICONTROL 数値概要] ビジュアライゼーション {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="概要番号"
>abstract="合計と小計を表示するビジュアライゼーションを作成します。"

<!-- markdownlint-enable MD034 -->

[!UICONTROL 数値概要] ビジュアライゼーションを使用すると、プロジェクトで重要になる大きな数値をハイライト表示できます。このビジュアライゼーションは、次のように動作します。

* セルが選択されていない場合、列の合計が選択されます。
* 1 つのセルが選択されている場合、そのセルの概要が表示されます。
* 2 つ以上のセルが選択されている場合、選択された最初のセルについて表示されます。
* 列が選択されている場合、列に含まれている先頭のセルの値が選択されます。

右上の「**ビジュアライゼーション設定**」の歯車をクリックして、概要番号の設定を指定します。

| 設定 | 定義 |
|--- |--- |
| [!UICONTROL 割合 (％)] | 生の数値ではなく、パーセンテージを表示します。 |
| [!UICONTROL 凡例を表示] | 表示された指標に関する情報を表示します。 |
| [!UICONTROL 値を短縮] | 値の表記を短縮して小数点以下 3 桁まで表示することを選択します。 |
| [!UICONTROL 値の要約基準] | 選択したデータの最大値、最小値、平均値、中央値または合計値の表示を選択します。 |

## [!UICONTROL 変更概要] ビジュアライゼーション {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="変更の概要"
>abstract="2 つの数値間の差分（変化）を表示するビジュアライゼーションの作成"

<!-- markdownlint-enable MD034 -->

[!UICONTROL 変更概要] ビジュアライゼーションを使用すると、2 つの数値間の差分（変化）を表示できます。[!UICONTROL 変更概要] の緑と赤の色は、 [カスタムイベントの極性](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) または計算指標の「[上昇傾向を次の形式で表示](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=ja)」オプションを使用して制御できます。

このビジュアライゼーションは、次のように動作します。

* セルが選択されていない場合、列に含まれている最初の 2 つのセル値が比較されます。
* 1 つのセルが選択されている場合、0 が表示されます。これは、そのセル値自体との比較がおこなわれるからです。
* 2 つのセルが選択されている場合、最初に選択したセルが分子、2 番目のセルが分母として処理されます。
* 3 つ以上のセルが選択されている場合、最初の 2 つのセルのみが比較の対象になります。
* 一定範囲のセルが選択されている場合、選択された範囲内の最初と最後のセルが比較されます。
* 列が選択されている場合、先頭の値がそれ自体と比較されます。その結果、変更は 0 と表示されます。


![](assets/summary-change.png)


右上の **ビジュアライゼーション設定** の歯車をクリックして、変更概要の設定を指定します。

| 設定 | 定義 |
| --- | --- |
| [!UICONTROL 割合 (％)] | 生の数値ではなく、パーセンテージを表示します。 |
| [!UICONTROL 凡例を表示] | 表示された指標に関する情報を表示します。 |
| [!UICONTROL 変化率を表示] | 2 つの数値間の変化率を表示します。 |
| [!UICONTROL 生の差異を表示] | 2 つの数の間の生の差異を表示します。また、値の省略形を使用し、小数点以下 3 桁まで表示できます。 |
