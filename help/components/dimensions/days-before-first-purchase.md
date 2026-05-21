---
title: 初回購入までの日数
description: 訪問者の初回訪問から初回購入までの日数。
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 83%

---

# 初回購入までの日数

「最初の購入までの日数」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者が初めてサイトにアクセスしてから購入するまでの日数をレポートします。 例えば、訪問者が最初の訪問の 1 日後に購入した場合、それ以降の訪問またはイベントはすべて「1 日」ディメンション項目に属します。

最初に購入した後、その訪問者は cookie の有効期間が切れるまで同じディメンション項目に属します。

## このディメンションへのデータ入力

アドビは、実装の [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) イベントに基づいて、このディメンションを自動的に設定します。 サイトに `purchase` イベントを実装する場合、このディメンションは常に機能します。

## ディメンション項目

ディメンション項目には、訪問者がサイトを初めて訪問してから最初に購入するまでの日数が含まれます。 各日数は個別のディメンション項目です。「同じ日」は、訪問者の初回訪問と初回購入が同じ日に発生した場合に発生します。
