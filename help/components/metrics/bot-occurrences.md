---
title: ボットの発生件数
description: ボットルールに一致したヒットの数。
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# ボットの発生件数

「ボット発生件数」 [指標](overview.md) 一致したヒット数を示します [ボットルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

ボットレポートは他のレポートスイートデータとは区切られるので、この指標は次のディメンションでのみ機能します。

* [ボット名](../dimensions/bot-name.md)
* [ページ](../dimensions/page.md)
* 時間ベースのディメンション ( 例： [日](../dimensions/day.md), [週](../dimensions/week.md)または [月](../dimensions/month.md))

この指標で他のディメンションを使用しても、データは返されません。

## この指標の計算方法

Adobeは、すべてのヒットをチェックして、組織が設定したボットルールと一致するかどうかを確認します。 特定のヒットがボットルールと一致する場合、そのヒットはレポートから除外され、この指標は 1 ずつ増加します。 この指標には、両方のページビュー ([`t()`](/help/implement/vars/functions/t-method.md)) およびリンクトラッキングヒット ([`tl()`](/help/implement/vars/functions/tl-method.md))、一方で [ボットページビュー数](bot-page-views.md) リンクトラッキングヒットは含めないでください。
