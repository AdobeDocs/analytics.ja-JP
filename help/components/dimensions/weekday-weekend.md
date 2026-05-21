---
title: 平日／週末
description: ヒットが平日または週末のどちらで発生したかを指定します。
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 80%

---

# 平日／週末

&#39;Weekday/Weekend&#39; [&#x200B; ディメンション &#x200B;](overview.md)は、平日（月曜日～金曜日）または週末（土曜日～日曜日）にヒットが発生したかどうかをinsightに提供します。 ヒットの時刻は、[レポートスイートのタイムゾーン](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)に基づいています。

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。 レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

このディメンションには、常に `"Weekday"` と `"Weekend"` の 2 つのディメンション項目が含まれます。 `"Weekday"` ディメンション項目は月～金曜日のすべてのヒットに適用され、`"Weekend"` ディメンション項目は土曜日と日曜日のすべてのヒットに適用されます。
