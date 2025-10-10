---
title: ボット名
description: ボットルールに一致したボットの名前。
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# ボット名

「ボット名」 [&#x200B; ディメンション &#x200B;](overview.md) には、[&#x200B; ボットルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) を使用して検出されたボットの名前が表示されます。 これらのルールは、デフォルトの IAB ルールでも、組織が設定するカスタムボットルールでも構いません。 これは、サイトを訪問しているボットや、最もトラフィックが多いボットについて詳しく知りたい場合に便利です。

[!UICONTROL &#x200B; ボットルール &#x200B;] に一致するヒットは、このディメンション、[&#x200B; ボットの発生 &#x200B;](../metrics/bot-occurrences.md)、[&#x200B; ボットページビュー &#x200B;](../metrics/bot-page-views.md) を除くすべての Analytics レポートから自動的に除外されます。 このディメンションとこれら 2 つの指標を使用して、残りのレポートから除外されているボットデータを確認できます。

ボットレポートは残りのレポートスイートデータから分離されているので、このディメンションでは次のディメンションと指標のみがサポートされます。

* [ページ](page.md)
* 時間ベースのディメンション（例：[&#x200B; 日 &#x200B;](day.md)、[&#x200B; 週 &#x200B;](week.md)、[&#x200B; 月 &#x200B;](month.md)）
* [ボットの発生件数](../metrics/bot-occurrences.md)
* [ボットページビュー数](../metrics/bot-page-views.md)

このディメンションで他のディメンションまたは指標を使用しても、データは返されません。

## このディメンションへのデータ入力

[&#x200B; ボットルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) を有効にしている場合、このディメンションはデータを自動的に収集します。 [!UICONTROL &#x200B; ボットルール &#x200B;] をまだ有効にしていない場合、このディメンションはAnalysis Workspaceに表示されません。

## ディメンション項目

各ディメンション項目には、IAB またはカスタムボットルールの条件に一致したボットの名前がリストされます。
