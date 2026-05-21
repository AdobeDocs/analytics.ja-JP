---
description: 複数のリクエストでマッピングされたセルをコピーして貼り付ける方法について説明します。
title: リクエストのコピー方法の概要
uuid: 1e0274a3-2038-45c7-87c8-bd949538d4e1
feature: Report Builder
role: User, Admin
exl-id: 14578c79-a9e6-4587-b91b-f590453df347
TQID: https://experienceleague.adobe.com/9HsICf4VKtAaDlime8Y9RAJjEPCra-KvMpIhUedBpWc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 144
ht-degree: 17%

---

# リクエストのコピーの概要

{{legacy-arb}}

リクエストにマッピングされているセルをコピーして、スプレッドシートで選択されている空の領域にその内容を貼り付けることができます。

セルをコピーした後、Report BuilderとExcelによって、コピーの最小量をペーストするために必要な領域が決まります。 領域が十分に大きい場合は、貼り付けによってすべてのリクエストのコピーが作成されます。貼り付けられた各リクエストは、元のリクエストと同じ空間配置と形式になります。

これは、リクエストの伝搬と呼ばれます。 これは、長いレポートを簡単かつ迅速に作成する方法です。 Report Builderでは、まず、対象の貼り付け領域のセル内のすべてのリクエストを貼り付けてリクエストを反映し、次に、リクエストに対して設定されたレポート日付に基づいてセルを更新します。
