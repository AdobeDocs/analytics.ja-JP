---
title: 初回購入までの日数
description: 訪問者の初回訪問から初回購入までの日数。
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
ht-degree: 63%
---
# 初回購入までの日数

「最初の購入までの日数」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者が初めてサイトにアクセスしてから購入するまでの日数をレポートします。 例えば、訪問者が最初の訪問の 1 日後に購入した場合、それ以降の訪問またはイベントはすべて「1 日」ディメンション項目に属します。

訪問者が初めて購入を行うと、その後は cookie の有効期間中ずっと同じディメンション項目に属することになります。

## このディメンションへのデータ入力

Adobeは、訪問者の購入履歴からサーバーサイドでこのディメンションを計算します。 設定する変数はありません。サイトで実装されている[`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) イベントによって異なります。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 訪問者 |

## ディメンション項目

ディメンション項目には、訪問者がサイトを初めて訪問してから最初に購入するまでの日数が含まれます。 各日数は個別のディメンション項目です。「同じ日」は、訪問者の初回訪問と初回購入が同じ日に発生した場合に発生します。
