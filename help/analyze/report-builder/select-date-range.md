---
title: Report Builderでデータ範囲を選択します
description: Report Builderで日付範囲を選択する方法を説明します。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 610ce2c8-8ff6-4434-912f-3015cc56a51e
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 46%

---

# 日付範囲の選択

既存のデータブロックの日付範囲を変更するには：

- **[!UICONTROL データブロックの編集]** を選択する
- **[!UICONTROL クイック編集]** の **[!UICONTROL 日付範囲]** リンクを選択します。

データブロックの日付範囲を変更するには、次のオプションを使用します。

## カレンダー

**[!UICONTROL カレンダー]** オプションでは、次のオプションを使用して、固定日付または相対日付を作成できます。

### 日付範囲

日付範囲フィールドには、データブロックリクエストに応じた現在の日付範囲が表示されます。 日付を直接入力するか、![&#x200B; カレンダー &#x200B;](/help/assets/icons/Calendar.svg) を使用して日付範囲を指定できます。

![&#x200B; 日付範囲カレンダー &#x200B;](assets/date-range-calendar.png){zoomable="yes"}

### プリセット

プリセット ドロップダウンメニューを使用して、プリセットを選択します。 また、テキストを入力してプリセットを検索することもできます。

![&#x200B; 日付範囲のプリセット &#x200B;](assets/date-range-presets.png){zoomable="yes"}

プリセットドロップダウンメニューには、標準のプリセット日付範囲と、保存したレポートスイートまたは共有したレポートスイートの日付範囲コンポーネントが含まれています。

### 相対日付

相対日付を定義する手順は、次のとおりです。

![&#x200B; 相対日付 &#x200B;](assets/date-range-rolling-date.png){zoomable="yes"}

1. **[!UICONTROL 相対日付を使用]** を選択して、相対日付の定義のロジックを定義します。 角括弧で囲まれたテキスト（例：**[!UICONTROL 固定開始 – 日周期]**）を選択して、パネルを拡張し、**[!UICONTROL 開始]** と **[!UICONTROL 終了]** の詳細を指定できます。

1. 「**[!UICONTROL 開始日]**」、「**[!UICONTROL 終了日]**」または「**[!UICONTROL 固定日]**」を選択します。

   - 「**[!UICONTROL 開始日]**」または「**[!UICONTROL 終了日]**」を選択すると、完全な式を作成できます。例：**[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**。式の個々の部分に適した値を選択します。

      - 現在の値を選択します。例えば、**[!UICONTROL 現在の年]** です。
      - オプションの追加計算の値を選択します。 例：**[!UICONTROL plus]**。
      - 追加の計算を指定した場合は、値を指定します。例：`1`。
      - 追加の計算を指定した場合は、計算に使用する期間を選択します。例えば、**[!UICONTROL day]** と指定します。

   - **[!UICONTROL 固定日]** を選択した場合は、固定日を指定するか、ピッカーを使用して日を選択します。

1. 相対日付計算の詳細を非表示にするには、「**[!UICONTROL 非表示]**」を選択します。


### カスタム式

「カスタム式」オプションを使用すると、カスタム式を作成するか、数式を入力して日付範囲を変更できます。

![&#x200B; 日付範囲のカスタム式 &#x200B;](assets/date-range-custom-expression.png){zoomable="yes"}

1. 「**[!UICONTROL 相対日付を使用]**」を選択します。

1. 「**[!UICONTROL カスタム式の使用]**」を選択します。

   **[!UICONTROL カスタム式の使用]** を選択すると、標準の相対日付範囲コントロールは無効になります。

1. [&#x200B; カスタム式 &#x200B;](#create-a-custom-expression) を入力します。

1. **[!UICONTROL 日付プレビュー]** を使用して、結果の日付範囲を確認します。

#### カスタム式の作成

1. [&#x200B; 日付参照 &#x200B;](#date-references) を入力します。

1. オプションの [&#x200B; 日付演算子 &#x200B;](#date-operators) を追加して、日付を過去または未来に移動します。

`tm-11m-1d` など、複数の演算子を含むカスタム式を入力できます。

#### 日付参照

次のテーブルに、日付参照の例を示します。

| 日付参照 | タイプ | 説明 |
|----------------|--------------|----------------------------|
| `1/1/10` | 静的な日付 | ISO 日付形式で入力 |
| `td` | 相対日付 | 本日の開始時 |
| `tw` | 相対日付 | 今週の開始日 |
| `tm` | 相対日付 | 今月の開始日 |
| `tq` | 相対日付 | 今四半期の開始日 |
| `ty` | 相対日付 | 今年の開始日 |

#### 日付演算子

次のテーブルに、日付演算子の例を示します。

| 日付演算子 | 単位 | 説明 |
|----------------|---------|--------------------|
| `+6d` | 日 | 日付参照に 6 日間を追加 |
| `+1w` | 週 | 日付参照に 1 週間を追加 |
| `-2m` | 月 | 日付参照から 2 か月を減算 |
| `-4q` | 四半期 | 日付参照から 4 四半期を減算 |
| -`1y` | 年 | 日付参照から 1 年を減算 |

#### 日付式

次のテーブルに、日付式の例を示します。

| 日付式 | 意味 |
|-----------------|--------------------------------------|
| `td` | Today |
| `td-1w` | 先週の最初の日 |
| `tm-1d` | 先月の最終日 |
| `td-52w` | 52 週間前の同じ曜日 |
| `tm-11m-1d` | 昨年同月の最終日 |
| `"2020-09-06"` | 2020 年 9 月 9 日（PT） |



## セルからの日付範囲

日付範囲は、ワークシートのセルで指定できます。「**[!UICONTROL セルからの日付範囲]**」オプションを使用して、選択したセルからデータブロックの開始日と終了日を選択します。 「**[!UICONTROL セルから]**」オプションを選択すると、パネルに **[!UICONTROL 開始]** フィールドと **[!UICONTROL 終了]** フィールドが表示されます。これらのフィールドで、セルの場所を入力したり、![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) を使用して現在選択されているセルを選択したりできます。

![&#x200B; セル シート 1!H4 からシート 1!I4 を選択 &#x200B;](./assets/date-range-from-cell.png){zoomable="yes"}


## 今日を除外

「**[!UICONTROL 今日を除外]**」を選択して、選択した日付範囲から今日を除外します。 現在の日付は、日付範囲（カレンダー、相対日付またはカスタム式）を定義するために使用されるすべてのモードから除外されます。


## 有効な日付範囲

次のリストは、有効な日付範囲の形式を示しています。

- 開始日と終了日は、「YYYY-MM-DD」の形式で指定する必要があります。

- 開始日は、終了日以前にする必要があります。どちらの日付も将来の日付に設定できます。

- 相対な日付を使用する場合は、開始日を今日または過去の日付にする必要があります。**[!UICONTROL 今日を除外]** を選択した場合、開始日は過去にする必要があります。

- 将来の静的な日付範囲セットを作成できます。例えば、来週予定されているマーケティングキャンペーンのローンチに、将来の日付を設定する必要が出ることがあります。このオプションを選択すると、事前にキャンペーンを監視するワークブックが作成されます。

## 日付範囲の変更

既存のデータブロックの日付範囲を編集できます。

1. データブロックのセルを選択します。

- **[!UICONTROL コマンド]** パネルの「**[!UICONTROL データブロックを編集]**」を選択するか、
- **[!UICONTROL クイック編集]** パネルの **[!UICONTROL 日付範囲]** リンクを選択します。

1. 使用可能な任意の日付選択オプションを使用して日付範囲を変更します。

1. 「**[!UICONTROL 適用]**」を選択します。

Report Builder は、選択範囲内のすべてのデータブロックに新しい日付範囲を適用します。

<!--
To change the date range of an existing data block, select Edit a data block or use the QUICK EDIT panel.

Use the following options to change a date range for a data block.

**Calendar**

 The Calendar allows you to create static or rolling dates using the following options:

- Date range field
- Calendar
- Preset drop-down menu
- Rolling date mode
- Customize expressions


**From cell**

The **[!UICONTROL From cell]** option allows you to reference dates entered in worksheet cells.

You have the option to exclude today on any selected date range.

 ![Report Builder Quick edit pane with calendar selected and Exclude today selected.](./assets/image17.png)

## Use the Calendar

When you use the **Calendar**, the date range field displays the current date range for the data block request. You can enter dates directly into the date range field or use a data range selection option.

### Date range field

To enter dates directly into the date range field

1. Click the date range field next to the calendar icon.

1. Enter start and end dates for your date range.

### Calendar

To select dates using the calendar

1. Click the calendar icon to display a monthly calendar.

1. Click a start date.

1. Click an end date.

To set a date range in reverse, click the end date first and then click the start date.

![Report Builder date range pane showing the calendar and the end date and the start date selected.](./assets/image18.png)

### Preset drop down menu

The preset drop-down menu includes a standard set of preset date ranges and date range components for a report suite that you saved or a report suite that was shared with you.

### Rolling dates

The rolling dates option allows you to select a date range using rolling dates.

1. Select **Use rolling dates**.

1. Select a rolling expression for your start and or end date.

    ![Report Builder date range pane showing Use rolling dates selected and the rolling expression.](./assets/image19.png)

    **Start of** — Allows you to select the beginning of a day, week, month, quarter, or year.

    **End of** — Allows you to select the end of a day, week, month, quarter, or year.

    **Fixed day** — Allows you to fix a start or end date while the other date is rolling.

1. Choose day, week, month, quarter, or year as the rolling period.

    ![Report Builder date range pane showing the current day selected.](./assets/image20.png)

1. Add or subtract days, weeks, months, quarters, or years from your rolling date.

    ![Report Builder date range pane showing the current day plus 14 days selected.](./assets/image21.png)

1. Click Next to define the data range.

    Use the date preview to confirm the resulting date range is the desired range.

### Custom expressions

The custom expression option allows you to change the date range by building a custom expression or you can enter an arithmetic formula.

1. Select **Use rolling dates**.

1. Select **Use custom expression**.

    When you select the **Use custom expression** option, the standard rolling date range controls are disabled.

    ![Select Use custom expression showing tm-1m to td-1d.](./assets/custom_expression.png)

1. Enter a custom expression.

    For a sample list of custom expressions, see **Date expressions**.

1. Use the date preview to verify the resulting date range is the desired range.

#### Create a custom expression

1. Enter a **Date reference**.

1. Add **Date operators** to move the date to the past or future.

You can enter a custom date expression that includes multiple operators, such as ```tm-11m-1d```.

#### Date references

The following table lists date reference examples.

| Date Reference | Type         | Description                |
|----------------|--------------|----------------------------|
| 1/1/10         | Static Date  | Entered in ISO Date format |
| td             | Rolling Date | Start of current day       |
| tw             | Rolling Date | Start of current week      |
| tm             | Rolling Date | Start of current month     |
| tq             | Rolling Date | Start of current quarter   |
| ty             | Rolling Date | Start of current year      |

#### Date operators

The following table lists date operator examples.

| Date Operators | Unit    | Description   |
|----------------|---------|--------------------|
| +6d            | Day     | Add 6 days to the Date Reference |
| +1w            | Week    | Add one full week to the Date Reference |
| -2m            | Month   | Subtract 2 full months to the Date Reference |
| -4q            | Quarter | Subtract 4 quarters to the Date Reference |
| -1y            | Year    | Subtract one year to the Date Reference |

#### Date expressions

The following table lists date expression examples.

| Date Expression | Meaning                              |
|-----------------|--------------------------------------|
| td-1w           | First day of last week               |
| tm-1d           | Last day of previous month           |
| td-52w          | Same day, 52 weeks ago               |
| tm-11m-1d       | Last day of the same month last year |
| "2020-09-06"    | Sept 9th, 2020                       |

## Date range from cell

The date range can be specified in worksheet cells. Use the **Date range from cell** option to choose the data block start and end date from selected cells. When you select the **From cell** option, the panel displays **From** and **To** fields where you can enter a cell location.

![Select From cell Sheet1!H4 to Sheet1!I4](./assets/image23.png)

## Exclude today

Choose the **Exclude today** option to exclude today from a selected date range. Choosing to include today may pull incomplete data for today.

When selected, the **Exclude today** option excludes the current day from all date range modes including calendar, rolling dates, or custom expressions.

## Valid date ranges

The following list describe valid date range formats.

- The start and end dates must be in the following format: YYYY-MM-DD

- The start date must be earlier to or equal to the end date. Both dates can be set to the future.

- When using rolling dates, the start date must be today or in the past. It must be in the past if **Exclude today** is checked.

- You can create a static date range set for the future. For example, you may need to set a future date for a marketing campaign launch next week. This option creates a workbook monitoring for a campaign ahead of time.

## Change the date range

You can edit the date range of an existing data block by selecting Edit data block in the COMMANDS panel or by selecting the date range link in the QUICK EDIT panel.

**Edit data block** — Allows you to edit multiple data block parameters, including date range, for a single data block.

**Quick Edit: Date range** — Allows you to edit the date range of one or more data blocks.

To edit the date range from the QUICK EDIT panel

1. Select cells within one or more data blocks in a worksheet.

1. Click the **Date range** link in the QUICK EDIT panel.

1. Select the date range using any of the date selection options.

1. Click **Apply**.


Report Builder applies the new date range to all data blocks in the selection.
-->