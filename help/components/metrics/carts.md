---
title: 買い物かご
description: 訪問者が最初の製品を買い物かごに追加したヒットの数。
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
TQID: https://experienceleague.adobe.com/a-qT5Ly8-4mSBGbGTAzbwLIMRFZtqotMPvGFgOrM41Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 45%

---

# 買い物かご

「買い物かご」の[指標](overview.md)には、訪問者が買い物かごに最初の商品を追加したヒット数が表示されます。

## この指標の計算方法

この指標は、`scOpen` が [`events`](/help/implement/vars/page-vars/events/events-overview.md) 変数に存在するヒット数をカウントします。

## 「買い物かご」、「買い物かご表示」、「買い物かご追加」の違い

「買い物かご」、「買い物かご表示」、「買い物かご追加」は実装を必要とするイベントであるため、組織はこれらの指標の正確な違いを決定します。 ただし、Adobeは次のロジックに対してこれらの指標を設計しました。

* 「買い物かご」は、訪問者が買い物かごに最初の製品を追加した場合に、購入ごとに 1 回だけトリガーされます。
* 訪問者がショッピングカートを閲覧するたびに「カート表示」トリガーが表示されます。
* 買い物かごに追加された各製品の「買い物かごへの追加」トリガー。

顧客が最初の商品をショッピングカートに追加すると、意図された動作は、「カート」と「カート追加」の両方のトリガーになります。 繰り返しますが、これらのガイドラインは具体的なものではありません。組織が正確な実装ロジックを決定します。
