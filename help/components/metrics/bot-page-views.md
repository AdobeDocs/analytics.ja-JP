---
title: ボットページビュー数
description: ボットルールに一致したページビューの数。
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# ボットページビュー数

「ボットページビュー数 [&#x200B; 指標 &#x200B;](overview.md) は、「ボットルール [&#x200B; に一致したページヒット数を表示 &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) ます。

ボットレポートは残りのレポートスイートデータから分離されているので、この指標は次のディメンションでのみ機能します。

* [ボット名](../dimensions/bot-name.md)
* [ページ](../dimensions/page.md)
* 時間ベースのディメンション（例：[&#x200B; 日 &#x200B;](../dimensions/day.md)、[&#x200B; 週 &#x200B;](../dimensions/week.md)、[&#x200B; 月 &#x200B;](../dimensions/month.md)）

この指標で他のディメンションを使用しても、データは返されません。

## この指標の計算方法

Adobeは、すべてのページヒットをチェックして、組織が設定したボットルールに一致するかどうかを確認します。 特定のヒットがボットルールに一致する場合、ページヒットはレポートから除外され、この指標は 1 増加します。 この指標には、リンクトラッキングヒット数（[`tl()`](/help/implement/vars/functions/tl-method.md)）は含まれません。
