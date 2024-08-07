---
title: ページでの滞在時間
description: 訪問者がページに滞在した時間。
feature: Dimensions
exl-id: 55af7286-7c37-48d2-925e-8b7ecb390e7f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 85%

---

# ページでの滞在時間

「ページでの滞在時間 [ ディメンション ](overview.md) は、訪問者がページで費やした時間を記録します。 次の手順を使用して計算を測定します。

1. 特定のヒットについて、タイムスタンプを確認します。
2. このヒットを、訪問の次のヒットのタイムスタンプと比較します。ページビューとリンクトラッキングのヒット数の両方。
3. この 2 つのヒット間の経過時間が、滞在時間に寄与します。

このディメンションは、訪問者がサイト上の特定の指標とどの程度の時間やり取りをするかを把握する場合に役立ちます。

>[!TIP]
>
>その後のイメージリクエストでは経過時間を測定しないので訪問の最後のヒット時には滞在時間は測定されません。この概念は、単一のヒット（バウンス）から成る訪問にも適用されます。

このディメンションはヒットに基づいています。つまり、ヒットごとに値が異なります。このディメンションを、[訪問別滞在時間](time-spent-per-visit.md)（訪問ベースのディメンション）と比較します。滞在時間が長いと、訪問者が 1 ページ（ヒット）に長く滞在したことを意味します。

![ページでの滞在時間](../metrics/assets/time-spent2.png)

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

ページでの滞在時間に対して複数のディメンションが存在します。

* **ページでの滞在時間 — グループ**：時間がグループ化されます。ディメンション項目の範囲は `"Less than 15 seconds"` ～ `"More than 30 minutes"` です。ヒット間の時間は通常、30 分以下です。ただし、タイムスタンプ付きのヒットまたはデータソースを使用する場合、ヒット間の時間は 30 分を超える場合があります。
* **ページでの滞在時間 — 詳細**：各秒数は、一意のディメンション項目です。

滞在時間の一般情報について詳しくは、[滞在時間の概要](../metrics/time-spent.md)を参照してください。
