---
title: 発生件数
description: 変数が設定または持続されたヒットの数。
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 64%

---

# 発生件数

「発生件数」 [指標](overview.md) 特定のディメンションが設定または持続されたヒット数を示します。 Workspace でディメンションを空白のキャンバスにドラッグすると、Adobe はこの指標を自動的にプロジェクトに適用します。

## この指標の計算方法

レポートスイート内のすべてのヒットの中で、ディメンション項目が定義または持続するヒットを含めます。[eVars](../dimensions/evar.md)などのディメンションは、設定されたヒットの後も保持される場合があります。この指標では、初期値と持続値の両方がカウントされます。

## 類似の指標と比較

* **発生件数と[インスタンス](instances.md)**：発生件数は、ディメンション項目が設定または持続されたヒットをカウントします。ディメンション項目が持続するヒットは、インスタンスに含まれません。
* **発生件数と [ページビュー数](page-views.md)**：発生件数には、ページビュートラッキングコール ([`t()`](/help/implement/vars/functions/t-method.md))、リンクトラッキングコール ([`tl()`](/help/implement/vars/functions/tl-method.md))、および概要からのデータ [データソース](/help/import/data-sources/overview.md). ページビュー数指標には、リンクトラッキングコールおよび概要データソースを除く、ページビュートラッキングコールのみが含まれます。
