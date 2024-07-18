---
title: ボットページビュー数
description: ボットルールに一致したページビューの数。
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# ボットページビュー数

「ボットページビュー数 [ 指標 ](overview.md) は、「ボットルール [ に一致したページヒット数を表示 ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) ます。

ボットレポートは残りのレポートスイートデータから分離されているので、この指標は次のディメンションでのみ機能します。

* [ボット名](../dimensions/bot-name.md)
* [ページ](../dimensions/page.md)
* 時間ベースのディメンション（例：[ 日 ](../dimensions/day.md)、[ 週 ](../dimensions/week.md)、[ 月 ](../dimensions/month.md)）

この指標で他のディメンションを使用しても、データは返されません。

## この指標の計算方法

Adobeは、すべてのページヒットをチェックして、組織が設定したボットルールに一致するかどうかを確認します。 特定のヒットがボットルールに一致する場合、ページヒットはレポートから除外され、この指標は 1 増加します。 この指標には、リンクトラッキングヒット数（[`tl()`](/help/implement/vars/functions/tl-method.md)）は含まれません。
