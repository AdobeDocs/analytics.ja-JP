---
title: 四半期
description: 年の四半期を、年に関係なく数値で表します。
feature: Dimensions
exl-id: 0de5f916-9cc1-4594-9dfc-68ef831dcc0a
TQID: https://experienceleague.adobe.com/a41aEgQ2NkPzWzcn59JfOd8LgL3vmhr1y11lsIwHpjI
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
source-wordcount: '172'
ht-degree: 62%
---
# 四半期

「年度の四半期」 [ ディメンション ](overview.md)は、任意の年の四半期をディメンション項目としてレポートします。 このレポートは、四半期ごとにレポートを分類し、ディメンション項目として静的な日付を必要としない場合に役立ちます。 四半期別に前年比レポートを集計できるので、この年の第 1 四半期のデータは昨年の第 1 四半期のデータと同じディメンション項目に集計されます。

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

ディメンション項目には、ヒットが発生した年の四半期を表す四半期数値（`1` ～ `4`）が含まれます。
