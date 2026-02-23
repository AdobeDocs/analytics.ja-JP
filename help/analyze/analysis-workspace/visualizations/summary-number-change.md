---
description: 概要番号および変更ビジュアライゼーションを使用して、プロジェクト内の重要なデータポイントを表示します。
title: 数値の概要と変更の概要
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 63%

---

# 数と変更の概要

>[!BEGINSHADEBOX]

_この記事は、_ AdobeAnalytics![ ](/help/assets/icons/AdobeAnalytics.svg)Adobe Analytics _**の数値概要と変更概要のビジュアライゼーションについて説明します**。_<br/>_この記事の [CustomerJourneyAnalytics](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change)_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) 版については、_**数値概要と変更概要** を参照してください。_

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [数値の概要と変更の概要ビジュアライゼーション](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/summary-number-and-summary-change-visualizations-2021){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

## 数値の概要 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="数値の概要"
>abstract="合計と小計を表示するビジュアライゼーションを作成します。"

<!-- markdownlint-enable MD034 -->

![要約](/help/assets/icons/123.svg) **[!UICONTROL 数値の概要]**&#x200B;ビジュアライゼーションを使用して、プロジェクト内の重要な多数の数値をハイライト表示します。このビジュアライゼーションは、関連付けられたデータソースを使用して、次のように動作します。

* セルが選択されていない場合に列の合計を選択します。
* 1 つのセルが選択されている場合は、そのセルの概要が表示されます。
* 複数のセルが選択されている場合は、最初に選択されたセルが表示されます。
* 列が選択されている場合は、列の最初のセル値が選択されます。

![数値の概要ビジュアライゼーション](asses/../assets/summary-number.png)

ビジュアライゼーション設定の一部として、特定の数値の概要オプションを使用できます。

| オプション | 定義 |
|--- |--- |
| **[!UICONTROL 値を短縮]** | 数値をインテリジェントに短縮するには、「**[!UICONTROL 値を短縮]**」を選択します。選択した場合、短縮の量を定義する数値を入力します。次に例を示します。<br/><table><tr><td>**元の値**</td><td>**短縮の値**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選択</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`0` に設定</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> 選択済み、`1` に設定</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`2` に設定</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`3` に設定</td><td align="right">$12.011M</td></tr></table> |
| **[!UICONTROL 値の要約基準]** | 選択したデータの最大値、最小値、平均値、中央値または合計値の表示を選択します。 |

## 変更の概要 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="変更の概要"
>abstract="2 つの数値間の差分（変化）を表示するビジュアライゼーションの作成"

<!-- markdownlint-enable MD034 -->


![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL 変更の概要]** ビジュアライゼーションを使用すると、2 つの数値間の差分（変化）を表示できます。<!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](/help/admin/tools/success-events/success-event.md) or a calculated metric's [Show Upward Trend As](/help/components/calculated-metrics/workflow/cm-build-metrics.md) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md.md) or a calculated metric's [Show Upward Trend As](/help/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.md) option.
-->

このビジュアライゼーションは、次のように動作します。

* セルが選択されていない場合は、列内の最初の 2 つのセル値が比較されます。
* 1 つのセルが選択されている場合は、そのセルの値と比較されるため、0 と表示されます。
* 2 つのセルが選択されている場合、最初に選択されたセルが分子、2 番目のセルが分母と見なされます。
* 3 つ以上のセルを選択すると、最初の 2 つのセルのみが比較の対象になります。
* セルの範囲が選択されている場合は、その範囲で最初のセルと最後に選択されているセルが比較されます。
* 列が選択されている場合は、最初の値がそれ自体と比較され、0 の変化が示されます。


![2 つの数値間の差分を示す変更の概要ビジュアライゼーション](assets/summary-change.png)


ビジュアライゼーション設定の一部として、特定の&#x200B;**[!UICONTROL 変更の概要オプション]**&#x200B;を使用できます。

| オプション | 定義 |
|--- |--- |
| **[!UICONTROL 変化率を表示]** | 2 つの数値間の変化率を表示します。 |
| **[!UICONTROL 生の差異を表示]** | 2 つの数値間の生の差異を表示します。また、値の省略形を使用し、小数点以下 3 桁まで表示できます。 |
| **[!UICONTROL 値を短縮]** | 変更した値をインテリジェントに短縮するには、「**[!UICONTROL 値を短縮]**」を選択します。選択した場合、短縮の量を定義する数値を入力します。次に例を示します。<br/><table><tr><td>**元の値**</td><td>**短縮の値**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選択</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`0` に設定</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> 選択済み、`1` に設定</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`2` に設定</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>選択済み、`3` に設定</td><td align="right">$12.011M</td></tr></table> |

>[!MORELIKETHIS]
>
>[パネルへのビジュアライゼーションの追加](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[ビジュアライゼーション設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[ビジュアライゼーションコンテキストメニュー](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
