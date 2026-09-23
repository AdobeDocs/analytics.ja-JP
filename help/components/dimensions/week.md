---
title: 週
description: 指標が発生した週。
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
TQID: https://experienceleague.adobe.com/Vvr0Svg2khSzWbtWR5hLfveyctOEM-62WU6oxIsvzXs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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
source-wordcount: '181'
ht-degree: 66%
---
# 週

「週」 [&#x200B; ディメンション &#x200B;](overview.md)は、特定の指標が発生した週をレポートします。 最初のディメンション項目は日付範囲の最初の週で、最後のディメンション項目は日付範囲の最後の週です。 このディメンションは、指標を経時的に確認できるため、トレンドレポートには不可欠です。

## このディメンションへのデータ入力

このディメンションは、各ヒットのタイムスタンプから派生します。 設定する変数はありません。任意の実装で標準搭載されています。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（ヒットタイムスタンプから派生） |
| **Web SDK / XDM フィールド** | なし（ヒットタイムスタンプから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | ヒット |

## ディメンション項目

Analysis Workspace では、ディメンション項目に週の最初の日付（月、日、年）が含まれます。

Data Warehouse では、ディメンション項目にリクエストの日付範囲に基づいて番号が付けられた週が含まれます。 例えば、1 週目は `"Week 1"` です。 リクエストに週の一部が含まれる場合、データはディメンションアイテム `"Week 0"` にグループ化されます。
