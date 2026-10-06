---
title: 製品発生の両方
description: 「ボット製品発生件数」指標は、ボットルールに一致し、Analytics レポートから除外された製品文字列サブヒットの数を示します。
feature: Metrics
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 3ba8d2cce29a1965c85789c3fd0543c23533e3a8
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%
---
# 製品発生の両方

「ボット製品発生数」の[指標](overview.md)には、[ ボットルール ](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)に一致したサブヒット数が表示されます。

ボットレポートはレポートスイートデータの残りの部分から分離されているため、この指標は次のディメンションでのみ機能します。

* [ボット名](../dimensions/bot-name.md)
* [製品](../dimensions/product.md)
* 時間ベースのディメンション （例：[日](../dimensions/day.md)、[週](../dimensions/week.md)、[月](../dimensions/month.md)）

この指標で他のディメンションを使用しても、データは返されません。

## この指標の計算方法

Adobeは、[製品文字列](/help/implement/vars/page-vars/products.md)を含むすべてのサブヒットをチェックして、組織が設定したボットルールに一致するかどうかを確認します。 特定のサブヒットがボットルールに一致した場合、サブヒットはレポートから除外され、この指標は1つ増加します。
