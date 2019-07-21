---
description: Excel の書式／セル（Ctrl + 1 キー）の機能で利用できる標準的なセル書式設定に加え、Report Builder を使用してセル範囲に対して簡易的な書式を適用できます。それらの書式設定に使用できるオプションは、選択した指標によって異なります。
seo-description: Excel の書式／セル（Ctrl + 1 キー）の機能で利用できる標準的なセル書式設定に加え、Report Builder を使用してセル範囲に対して簡易的な書式を適用できます。それらの書式設定に使用できるオプションは、選択した指標によって異なります。
seo-title: 日付の形式設定
solution: Analytics
title: 日付の形式設定
topic: Report Builder
uuid: 5211db30-07b3-4413-97c3- e40e6ff223cd
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 日付の形式設定

Excel の書式／セル（Ctrl + 1 キー）の機能で利用できる標準的なセル書式設定に加え、Report Builder を使用してセル範囲に対して簡易的な書式を適用できます。それらの書式設定に使用できるオプションは、選択した指標によって異なります。

After you [add dimensions](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) to the Row Labels grid, click **[!UICONTROL Format]**.

「**[!UICONTROL 書式]**」メニューで、「**カスタムフォーマット[!UICONTROL 」をクリックして、前付け／後付け機能と同様に、カスタマイズされた書式を日付に適用します。]**&#x200B;例えば、日付の後に常に付加されるテキスト（A.D.、B.C.E.、A.H. など）を入力することができます。また、日付の前に、「[!UICONTROL 開始日]」、「[!UICONTROL 開始・終了日]」などのテキストを追加することもできます。さらに、日、月、年の略語を使用してカスタムの日付式を作成し、日付の内部にカスタムの区切り文字を使用することができます。すべての日付書式は 3 つの略語で構成され、括弧で囲まれている必要があります。

次の表では、「[!UICONTROL カスタムフォーマット]」フィールドで日付の略語を使用する方法を説明します。

| 略語 | 意味 | 例   2012 年 3 月 14 日（水）の場合 |
|--- |--- |--- |
| MM/dd/yyy | 数字表記の正式な日付 | 03/14/2012 |
| M | 月 | 3 |
| MM | 月（10 未満の月の場合に 10 の位に 0 を付加） | 03 |
| MMM | 月の略称 | Mar |
| MMMM | 月の正式名称 | March |
| D | 日付の正式名称 | Wednesday, March 14, 2012 |
| d | 日 | 14 |
| dd | 日（10 未満の日の場合に 10 の位に 0 を付加） | 14 |
| ddd | 曜日の略称 | Wed |
| dddd | 曜日の正式名称 | Wednesday |
| yy | 2 桁表記の年 | 12 |
| yyyy | 4 桁表記の年 | 2012 |