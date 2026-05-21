---
title: 有料検索
description: 指標と有料検索および自然検索を区別します。
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 87%

---

# 有料検索

「有料検索」 [ ディメンション ](overview.md)を使用すると、任意の指標を見て、有料検索と自然検索を比較できます。 検索エンジン以外でのその他のヒットはすべて省略されます。 このディメンションは、有料検索とオーガニック検索との比較を理解するのに役立ちます。

## このディメンションへのデータ入力

このディメンションが正しく機能するための唯一の要件は、レポートスイートの設定で[有料検索検知](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)を正しく設定することです。 有料検索検知が正しく設定され、レポートスイートにデータが含まれている場合、このディメンションは常に機能します。

## ディメンション項目

ディメンション項目には `"Natural"` と `"Paid"` の 2 つの静的値が含まれます。 訪問が検索エンジンの条件と一致し、有料検索検出とも一致する場合、その訪問は `"Paid"` ディメンション項目に属します。 訪問が検索エンジンの条件と一致し、有料検索検出と一致&#x200B;*しない場合*、その訪問は `"Natural"` ディメンション項目に属します。
