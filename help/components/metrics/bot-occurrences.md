---
title: ボットの発生件数
description: ボットルールに一致したヒットの数。
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# ボットの発生件数

「ボットの発生件数 [ 指標 ](overview.md) は、[ ボットルール ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) に一致したヒット数を表示します。

ボットレポートは残りのレポートスイートデータから分離されているので、この指標は次のディメンションでのみ機能します。

* [ボット名](../dimensions/bot-name.md)
* [ページ](../dimensions/page.md)
* 時間ベースのディメンション（例：[ 日 ](../dimensions/day.md)、[ 週 ](../dimensions/week.md)、[ 月 ](../dimensions/month.md)）

この指標で他のディメンションを使用しても、データは返されません。

## この指標の計算方法

Adobeは、すべてのヒットをチェックして、組織で設定されているボットルールに一致するかどうかを確認します。 特定のヒットがボットルールに一致する場合、そのヒットはレポートから除外され、この指標は 1 増加します。 この指標には、ページビュー数（[`t()`](/help/implement/vars/functions/t-method.md)）とリンクトラッキングヒット数（[`tl()`](/help/implement/vars/functions/tl-method.md)）の両方が含まれますが、[ ボットページビュー数 ](bot-page-views.md) にはリンクトラッキングヒット数は含まれません。
