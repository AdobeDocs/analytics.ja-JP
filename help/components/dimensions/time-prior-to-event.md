---
title: イベント前の時間
description: 指標から訪問の最初のヒットまでの時間。
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 84%

---

# イベント前の時間

「イベント前の時間」ディメンション [1}は、訪問の最初のヒットから目的の指標までの間に経過した時間をレポートします。 ](overview.md)このディメンションは、フォームの送信や購入など、成功イベントに到達するまでの時間を判断するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、技術的にはすべての実装で初期設定の状態で機能しますが、カスタムおよび購入イベントで最も効果的です。 サイトにカスタムイベントを実装することをお勧めします。 カスタムイベントを実装する場合、このディメンションに追加の実装は必要ありません。

## ディメンション項目

ディメンション項目には、`"Less than 1 minute"` から `"More than 15 hours"` までの時間ベースのグループが含まれます。 例えば、最初のヒットから購入までに 23 分かかった訪問者は、`"10 to 30 minutes"` ディメンション項目の下に含まれます。 バケットは、この指標に対してカスタマイズできません。
