---
description: Excel の書式／セル（Ctrl + 1 キー）の機能で利用できる標準的なセル書式設定に加え、Report Builder を使用してセル範囲に対して簡易的な書式を適用できます。それらの書式設定に使用できるオプションは、選択した指標によって異なります。
title: 日付の書式
topic: Report builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 日付の書式

Excel の書式／セル（Ctrl + 1 キー）の機能で利用できる標準的なセル書式設定に加え、Report Builder を使用してセル範囲に対して簡易的な書式を適用できます。それらの書式設定に使用できるオプションは、選択した指標によって異なります。

After you [add dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) to the Row Labels grid, click **[!UICONTROL Format]**.

In the **[!UICONTROL Format]** menu, click **[!UICONTROL Custom Format]** to apply customized formats for dates similar to the prepend and postpend feature. 例えば、日付の後に常に付加されるテキスト（A.D.、B.C.E.、A.H. など）を入力することができます。日付の前に、やなどのテキストを追加で [!UICONTROL Start Date] きます [!UICONTROL Start and End Date]。 さらに、日、月、年の略語を使用してカスタムの日付式を作成し、日付の内部にカスタムの区切り文字を使用することができます。すべての日付書式は 3 つの略語で構成され、括弧で囲まれている必要があります。

The following table describes how you can use date abbreviations in the [!UICONTROL Custom Format] field:

| 略語 | 意味 | 例2012 年 3 月 14 日（水）の場合 |
|--- |--- |--- |
| MM/dd/yyy | 数字表記の正式な日付 | 03/14/2012 |
| M | 月 | 3 |
| MM | 月（10 未満の月の場合に 10 の位に 0 を付加） | 03 |
| MMM | 月の略称 | Mar |
| MMMM | 月の正式名称 |  年 3 月 |
| D | 日付の正式名称 | 2012 年 3 月 14 日水曜日 |
| d | 日 | 14 |
| dd | 日（10 未満の日の場合に 10 の位に 0 を付加） | 01 - 09 |
| ddd | 曜日の略称 | Wed |
| dddd | 曜日の正式名称 | 水曜日 |
| yy | 2 桁表記の年 | 10 |
| yyyy | 4 桁表記の年 | 2012 |
