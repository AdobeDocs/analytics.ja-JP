---
title: Experience Cloud の訪問者 ID
description: Data Warehouseで使用可能な、訪問者のExperience Cloud ID （ECID）。
feature: Dimensions
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 21%

---

# Experience Cloud の訪問者 ID

「Experience Cloud訪問者ID」 [ ディメンション ](overview.md)は、各訪問者にExperience Cloud ID （ECID）を提供します。 これは、連結された2つの64 ビット番号を19桁にパディングした128 ビット番号です。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。

## このディメンションへのデータ入力

このディメンションには、Experience Cloud ID サービス（ECID）を使用する実装が必要です。 データフィードの`mcvisid`列に対応します。 詳しくは、[ データ列リファレンス ](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)を参照してください。

## ディメンション項目

Dimensionの項目には、各訪問者のExperience Cloud IDが含まれます。
