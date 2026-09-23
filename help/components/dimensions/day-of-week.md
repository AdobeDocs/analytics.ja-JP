---
title: 曜日
description: 日付範囲に関係なく、曜日を表します。
feature: Dimensions
exl-id: 01aa6b5f-49e6-4f86-97c7-8d0ff431e15b
TQID: https://experienceleague.adobe.com/9nudTrYTDMEFXSo81uUuw9KFT3mRPhZer3cX81AwoPM
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
source-wordcount: '167'
ht-degree: 62%
---
# 曜日

「曜日」 [&#x200B; ディメンション &#x200B;](overview.md)は、ヒットが発生した曜日をレポートします。 このレポートは、週別にレポートを分類するが、ディメンション項目として静的な日数を必要としない場合に役立ちます。 このディメンションはどのような日付範囲でも機能するため、スケジュール済みレポートのディメンションとして特に有用です。

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

ディメンション項目には `Sunday` ～ `Saturday` が含まれ、ヒットが発生した曜日を表します。 ディメンション項目のデフォルト順序は、[カスタムカレンダー](/help/admin/tools/manage-rs/edit-settings/general/custom-calendar.md)の週の最初の曜日に従います。
