---
title: 通算訪問回数
description: 訪問者の n 回目の訪問。
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
TQID: https://experienceleague.adobe.com/C6fccfJFGSA4iLuhp2X80aPym4ZcwbrLMaUS2LUfosg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 77%
---
# 通算訪問回数

「通算訪問回数」[ディメンション](overview.md)は、訪問者の現在の訪問が通算で何回目の訪問に当たるかを示します。 新しい訪問が開始されると、このディメンション項目は 1 ずつ増加します。 このディメンションは、訪問者がサイトを再訪問したときに、どの程度エンゲージしているかを把握するのに役立ちます。 これは訪問ベースのディメンションです。つまり、同じ一つの訪問の間は同じ値が保持され、変更することはできません。 また、このディメンションは、プロジェクトの日付範囲に関係なく、訪問者の全期間にわたって適用されます。

## このディメンションへのデータ入力

Adobeは、訪問者の訪問履歴から、このディメンションをサーバーサイドで計算します。 設定する変数はありません。すべての実装に対してすぐに使用できます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 訪問 |

## ディメンション項目

ディメンション項目では、文字列 `"Visit number"` の後に、訪問者の現在の訪問が通算で何回目の訪問に当たるかを示す数値が続きます。 例えば、以前にサイトを訪問したことがない訪問者による最初の訪問は `"Visit number 1"` ディメンション項目に属します。 同じ訪問者による 13 回目の訪問である場合、その訪問は `"Visit number 13"` ディメンション項目に属します。
