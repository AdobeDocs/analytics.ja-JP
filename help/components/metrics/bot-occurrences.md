---
title: ボットの発生件数
description: ボットルールに一致したヒットの数。
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# ボットの発生件数

「ボットの発生件数 [&#x200B; 指標 &#x200B;](overview.md) は、[&#x200B; ボットルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) に一致したヒット数を表示します。

ボットレポートは残りのレポートスイートデータから分離されているので、この指標は次のディメンションでのみ機能します。

* [ボット名](../dimensions/bot-name.md)
* [ページ](../dimensions/page.md)
* 時間ベースのディメンション（例：[&#x200B; 日 &#x200B;](../dimensions/day.md)、[&#x200B; 週 &#x200B;](../dimensions/week.md)、[&#x200B; 月 &#x200B;](../dimensions/month.md)）

この指標で他のディメンションを使用しても、データは返されません。

## この指標の計算方法

Adobeは、すべてのヒットをチェックして、組織で設定されているボットルールに一致するかどうかを確認します。 特定のヒットがボットルールに一致する場合、そのヒットはレポートから除外され、この指標は 1 増加します。 この指標には、ページビュー数（[`t()`](/help/implement/vars/functions/t-method.md)）とリンクトラッキングヒット数（[`tl()`](/help/implement/vars/functions/tl-method.md)）の両方が含まれますが、[&#x200B; ボットページビュー数 &#x200B;](bot-page-views.md) にはリンクトラッキングヒット数は含まれません。
