---
description: Analysis Workspaceでの日付比較の使用方法を説明します。この方法を使用すると、日付範囲を含む任意の列を使用して、一般的な日付比較を作成できます。
title: 日付の比較
feature: Date Ranges
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: 3d15bd941cb8eaf20b8ae9f1ffa1dbfd403b2bfa
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 35%

---

# 日付の比較

Analysis Workspaceの日付比較を使用すると、日付範囲を含む任意の列を使用して、前年比、前四半期比、前月比などの一般的な日付比較を作成できます。

## 期間を比較

分析にはコンテキストが必要ですが、多くの場合、そのコンテキストは前の期間から得られます。例えば、*昨年の今の時期と比較して、今やっていることはどれくらい良い、または悪いですか？* れは、ビジネスを理解するための基本です。 日付比較には、指定した期間に対する変更率を示す *差分* 列が自動的に含まれます。

1. 一定期間にわたって比較するディメンションと指標を含んだ [ フリーフォームテーブル ](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) を作成します。
1. テーブルの行のコンテキストメニューを開き、「**[!UICONTROL 期間を比較]**」を選択します。

   ![ 「期間を比較」が選択されたテーブル行 ](assets/compare-time.png)

   >[!NOTE]
   >
   >このコンテキスト・メニュー・オプションは、メトリック行、日付範囲行および時間ディメンション行では無効です。

1. テーブルの日付範囲をどのように設定したかに応じて、次のオプションを比較に使用できます。

   | オプション | 説明 |
   |---|---|
   | **[!UICONTROL この日付範囲の前 *x* 週/月/四半期/年]** | 選択した日付範囲の直前の日付範囲と比較します。 |
   | **[!UICONTROL この日付範囲への過去 x 週間/月/四半期/年]** | 1 年前の同じ日付範囲と比較します。 |
   | **[!UICONTROL この日付範囲のカスタム日付範囲]** | カスタムの日付範囲を定義できます。 |

   >[!NOTE]
   >
   >例えば、10月7日～10月20日（14 日間の範囲）など、カスタムの日数を選択した場合、「**[!UICONTROL この日付範囲の 14日前]**」と「**[!UICONTROL この日付範囲のカスタム日付範囲]**」の 2 つのオプションのみが表示されます。

1. 結果として次のような比較が表示されます。

   ![ 日付範囲と変更率の比較を示すフリーフォームテーブル。](assets/compare-time-result.png)

   変更率の列の行は、負の値の場合は赤、正の値の場合は緑で表示されます。

## 比較のために期間の列を追加

テーブルの各列に期間を追加できるようになりました。これにより、カレンダーを設定した期間とは異なる期間を追加できます。

1. テーブルの列を右クリックし、「**[!UICONTROL 期間列を追加]**」を選択します。

   ![](assets/add-time-period-column.png)

1. テーブルの日付範囲をどのように設定したかに応じて、次のオプションを比較に使用できます。

   | オプション | 説明 |
   |---|---|
   | **[!UICONTROL この日付範囲の前 *x* 週/月/四半期/年]** | 週や月などを含んだ列を追加 比較します。 |
   | **[!UICONTROL 昨年の *x* 週/月/四半期/年をこの日付範囲に含める]** | 1 年前に同じ日付範囲を追加します。 |
   | **[!UICONTROL この日付範囲のカスタム日付範囲]** | カスタムの日付範囲を作成できます。 |

   >[!NOTE]
   >
   >例えば、10月7日～10月20日（14 日間の範囲）など、カスタムの日数を選択した場合、「**[!UICONTROL この日付範囲の 14日前]**」と「**[!UICONTROL この日付範囲のカスタム日付範囲]**」の 2 つのオプションのみが表示されます。

1. 期間は、選択した列の上に挿入されます。

   ![ 現在のカレンダー期間と前のカレンダー月における発生件数を示すフリーフォームテーブル。](assets/add-time-period-column2.png)

1. 期間の列はいくつでも追加でき、異なる日付範囲を組み合わせることもできます。

1. また、各列で並べ替えることもできます。これにより、並べ替える列に応じて日の順序を変更します。

## 列の日付が同じ行で始まるように整列

各列の日付をすべて同じ行から始まるように整列できます。

例えば、先週（2024 年 10 月 5 日まで）と前週の日比比較を行います。 デフォルトでは、左の列は 9 月 22 日（PT）、右の列は 9 月 29 日（PT）から始まります。

![ 日付が整列していない ](assets/not-align-dates.png)

**[!UICONTROL 設定]** で [ 各列の日付を同じ行からすべての日付が始まるように整列 ](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) を有効にすると、フリーフォームテーブルビジュアライゼーションは列の日付を同じ行から始まるように整列することができます。

![](assets/align-dates.png)

このオプションを使用する際は、次の点を考慮してください。

* この設定は、すべての新しいプロジェクトに対してデフォルトで有効になっています。

* この設定は、テーブル全体に適用されます。例えば、テーブル内の分類に対してこの設定を変更すると、テーブル全体に設定が適用されます。


<!--
# Date comparison

Date comparison in Analysis Workspace lets you take any column containing a date range and create a common date comparison, such as: year-over-year, quarter-over-quarter, month-over-month, etc.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Date comparison](https://video.tv.adobe.com/v/30753?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



## Compare time periods {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL Compare Time Periods] leverages advanced Calculated Metrics. As a result, it is available only to customers with Analytics Select, Prime, and Ultimate SKUs. 

Analysis requires context, and often that context is provided by a previous time period. For example, the question "How much better or worse are we doing than at this time last year?" is fundamental to understanding your business. Date Comparison automatically include a "difference" column, which shows the percentage change compared to a specified time period.

1. Create a Freeform table, with any dimensions and metrics you want to compare over a time period.
1. Right-click a table row and select **[!UICONTROL Compare time periods]**.

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >This right-click option is disabled for metric rows, date range rows, and time dimension rows.

1. Depending on how you have set the table's date range, you have these options for comparison: 

   |  Option  | Description  |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Compares to the week/month/etc. immediately before this date range.  |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Compares to the same date range a year ago.  |
   | **[!UICONTROL Custom date range to this date range]** | Lets you select a custom date range.  |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Custom date range to this date range]**.

1. The resulting comparison looks like this:

   ![](assets/compare-time-result.png)

   Rows in the Percent Change column appear red for negative values and green for positive values.

1. (Optional) As in any other Workspace projects, you can create visualizations based on these time comparisons. For example, here is a Bar graph:

   ![](assets/compare-time-barchart.png)

   Note that in order to show the percentage change in the bar chart, you have to have the [!UICONTROL Percentages] setting checked in the [!UICONTROL Visualization Settings].

## Add a time period column for comparison {#section_93CC2B4F48504125BEC104046A32EB93}

You can now add a time period to each column in a table, enabling you to add a time period that is different from the one your calendar is set to. This is another way you can compare dates.

1. Right-click a column in the table and select **[!UICONTROL Add time period column]**. 

   ![](assets/add-time-period-column.png)

1. Depending on how you have set the table's date range, you have these options for comparison: 

   |  Option  | Description  |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Adds a column with the week/month/etc. immediately before this date range.  |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Adds the same date range a year ago.  |
   | **[!UICONTROL Custom date range to this date range]** | Lets you select a custom date range.  |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Custom date range to this date range]**.

1. The time period will be inserted on top of the column you selected:

   ![](assets/add-time-period-column2.png)

1. You can add as many time columns as you want, as well as mix and match different date ranges:

   ![](assets/add-time-period-column4.png)

1. In addition, you can sort on each column, which will change the order of days depending on the column you are sorting on.

## Align column dates to start on the same row {#section_5085E200082048CB899C3F355062A733}

You can align the dates from each column to all start on the same row. 

For example, when you choose to align the dates, if you do a month-over-month comparison between October and September 2016, the left column will start with October 1 and the right column will start with September 1:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Consider the following when using this option:
>
>* This setting is enabled by default for all new projects.
>
>* This setting applies to the entire table. For example, if you change this setting for a breakdown within the table, it will change the setting for the entire table.
>

To enable this setting, if it is not already enabled:

1. In the table where you want to align column dates, select the **Settings** icon in the table header.

1. On the [!UICONTROL **Settings**] tab, select **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**.

![](assets/date-comparison-setting.png)


-->