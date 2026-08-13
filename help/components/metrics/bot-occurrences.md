---
title: ボットの発生件数
description: ボットルールに一致したヒット数。
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
TQID: https://experienceleague.adobe.com/LH7eQC-Z6Y3nku1QzI9Yn0N3MRwGA--5R-93lfadT1c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 9%

---

# ボットの発生件数

「ボットの発生回数」の[指標](overview.md)には、[&#x200B; ボットルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)に一致したヒット数が表示されます。

ボットレポートはレポートスイートデータの残りの部分から分離されているため、この指標は次のディメンションでのみ機能します。

* [ボット名](../dimensions/bot-name.md)
* [ページ](../dimensions/page.md)
* 時間ベースのディメンション （例：[日](../dimensions/day.md)、[週](../dimensions/week.md)、[月](../dimensions/month.md)）

この指標で他のディメンションを使用しても、データは返されません。

## この指標の計算方法

Adobeでは、あらゆるヒットをチェックし、組織が設定したボットルールに一致するかどうかを確認します。 特定のヒットがボットルールに一致した場合、そのヒットはレポートから除外され、この指標は1つ増加します。 この指標には、ページビュー（[`t()`](/help/implement/vars/functions/t-method.md)）とリンクトラッキングヒット（[`tl()`](/help/implement/vars/functions/tl-method.md)）の両方が含まれますが、[&#x200B; ボットページビュー](bot-page-views.md)にはリンクトラッキングヒットは含まれません。
