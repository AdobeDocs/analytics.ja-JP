---
title: ボット名
description: ボットルールに一致したボットの名前。
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# ボット名

「ボット名」 [ ディメンション ](overview.md) には、[ ボットルール ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) を使用して検出されたボットの名前が表示されます。 これらのルールは、デフォルトの IAB ルールでも、組織が設定するカスタムボットルールでも構いません。 これは、サイトを訪問しているボットや、最もトラフィックが多いボットについて詳しく知りたい場合に便利です。

[!UICONTROL &#x200B; ボットルール &#x200B;] に一致するヒットは、このディメンション、[ ボットの発生 ](../metrics/bot-occurrences.md)、[ ボットページビュー ](../metrics/bot-page-views.md) を除くすべての Analytics レポートから自動的に除外されます。 このディメンションとこれら 2 つの指標を使用して、残りのレポートから除外されているボットデータを確認できます。

ボットレポートは残りのレポートスイートデータから分離されているので、このディメンションでは次のディメンションと指標のみがサポートされます。

* [ページ](page.md)
* 時間ベースのディメンション（例：[ 日 ](day.md)、[ 週 ](week.md)、[ 月 ](month.md)）
* [ボットの発生件数](../metrics/bot-occurrences.md)
* [ボットページビュー数](../metrics/bot-page-views.md)

このディメンションで他のディメンションまたは指標を使用しても、データは返されません。

## このディメンションへのデータ入力

[ ボットルール ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) を有効にしている場合、このディメンションはデータを自動的に収集します。 [!UICONTROL &#x200B; ボットルール &#x200B;] をまだ有効にしていない場合、このディメンションはAnalysis Workspaceに表示されません。

## ディメンション項目

各ディメンション項目には、IAB またはカスタムボットルールの条件に一致したボットの名前がリストされます。
