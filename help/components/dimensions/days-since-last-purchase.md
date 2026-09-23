---
title: 前回購入からの日数
description: 現在のヒットから最後の購入までの日数。
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
source-wordcount: '207'
ht-degree: 64%
---
# 前回購入からの日数

「前回の購入からの日数」 [ ディメンション ](overview.md)は、訪問者の現在のヒットとその時点での最新の購入との間に経過した時間を測定します。 このディメンションは、サイトでの購入後に訪問者が実行する行動を把握するのに役立ちます。

1 回も購入したことのない訪問者は、このディメンションには含まれません。 また、訪問者の初回購入前に発生したヒットも含まれません。 訪問者の初回購入後のヒットのみが含まれます。

## このディメンションへのデータ入力

Adobeは、訪問者の購入履歴からサーバーサイドでこのディメンションを計算します。 設定する変数はありません。サイトで実装されている[`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) イベントによって異なります。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、訪問者の最終購入から現在のヒットまでの日数が含まれます。 各日数は個別のディメンション項目です。「同じ日」 は、訪問者の最後の購入と現在のヒットが同じ日に発生した場合に発生します。
