---
title: 新規エンゲージメント
description: ファーストタッチチャネルが設定された回数。
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
TQID: https://experienceleague.adobe.com/UsPu31wUqpoDYQy5aT9wnzSUgJ6i9mHVZ8pAtFQgzGo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 83%

---

# 新規エンゲージメント

「新規エンゲージメント」 [指標](overview.md)は、訪問者が訪問者のエンゲージメント期間中に初めてマーケティングチャネルに一致した回数を示します。 この指標は、任意のディメンションと、マーケティングチャネルの処理ルールに一致する訪問者を初めて比較する場合に役立ちます。

## この指標の計算方法

データ処理中は、すべてのヒットが[マーケティングチャネルの処理ルール](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)を通じて実行されます。 ヒットがどのマーケティングチャネルの処理ルールとも一致し、訪問者にファーストタッチチャネルがまだない場合、そのヒットは新しいエンゲージメントです。 ヒットがどのマーケティングチャネル処理ルールとも一致しない場合、または訪問者に既にファーストタッチチャネルがある場合、そのヒットは新規のエンゲージメントではありません。

訪問者は、訪問者のエンゲージメント期間を期限切れにした場合、複数の新規エンゲージメントを持つことができます。
