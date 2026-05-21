---
title: 分
description: 指標が発生した分。
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
TQID: https://experienceleague.adobe.com/GRivRprXBteGxRZieSI3uyjHALDJ-0hHbZx3S9ldJW0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 76%

---

# 分

「分」 [ ディメンション ](overview.md)は、特定の指標が発生した（切り捨てられた）分を報告します。 最初のディメンション項目は日付範囲の最初の分で、最後のディメンション項目は日付範囲の最後の分です。 このディメンションは、経時的に指標を見ることができる、トレンドレポートには役立ちます。 このディメンションの精度を考慮し、レポートの日付範囲を 1 ～ 2 日に制限することを推奨します。

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。 レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

ディメンション項目には、レポートの日付範囲内の指定した分が日付と共に含まれます。 `HH:MM YYYY-MM-DD` という形式で記述します。 `00:00`で始まるDimension項目は、その日の午前0時に相当し、`23:59`で始まる値はその日の午後11:59に相当します。
