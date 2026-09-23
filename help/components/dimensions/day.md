---
title: 日
description: 指標が発生した日。
feature: Dimensions
exl-id: 2f93ae8b-422c-4e1e-81d3-43cc0aa442c4
TQID: https://experienceleague.adobe.com/q9gioxGcmj2xB-yamZUyM3jLLlTpT4NHq1CFCMqm-6I
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
source-wordcount: '149'
ht-degree: 59%
---
# 日

「日」 [ ディメンション ](overview.md)は、特定の指標が発生した日をレポートします。 最初のディメンション項目は日付範囲の最初の日で、最後のディメンション項目は日付範囲の最後の日です。 このディメンションは、経時的に指標を見ることができる、トレンドレポートには不可欠です。

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

ディメンション項目には、特定の日付が含まれます。 月、日、年がディメンション項目の一部として含まれます。
