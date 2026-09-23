---
title: 月間通算日
description: どの月かに関係なく、月間通算日を表します。
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
TQID: https://experienceleague.adobe.com/jSrKlf4a5f-6MTrQwwUcvRJep4chAUyOsj5hFjE1HRg
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
source-wordcount: '180'
ht-degree: 63%
---
# 月間通算日

「月の日」ディメンション [1}は、任意の月の数値をディメンション項目としてレポートします。 ](overview.md)例えば、1 月 1 日から 3 月 31 日までのレポートがある場合、各月の 1 日は同じディメンション項目にグループ化されます。 このレポートは、日別にレポートを分類するが、ディメンション項目として静的な日数を必要としない場合に役立ちます。 このディメンションは、選択した日付範囲に合わせてスライドするため、定期レポートのディメンションとして特に有用です。

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

ディメンション項目には、ヒットが発生した日を表す数字 `1` ～ `31` が含まれます。
