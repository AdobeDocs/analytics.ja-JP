---
title: ボットページビュー数
description: ボットルールに一致したページビューの数。
feature: Metrics
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# ボットページビュー数

「ボットページビュー」 [指標](overview.md) 一致したページヒット数を示します [ボットルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

ボットレポートは他のレポートスイートデータとは区切られるので、この指標は次のディメンションでのみ機能します。

* [ボット名](../dimensions/bot-name.md)
* [ページ](../dimensions/page.md)
* 時間ベースのディメンション ( 例： [日](../dimensions/day.md), [週](../dimensions/week.md)または [月](../dimensions/month.md))

この指標で他のディメンションを使用しても、データは返されません。

## この指標の計算方法

Adobeは、各ページヒットをチェックして、組織が設定したボットルールと一致するかどうかを確認します。 特定のヒットがボットルールと一致する場合、ページヒットはレポートから除外され、この指標は 1 ずつ増加します。 この指標には、リンクトラッキングヒット ([`tl()`](/help/implement/vars/functions/tl-method.md)) をクリックします。
