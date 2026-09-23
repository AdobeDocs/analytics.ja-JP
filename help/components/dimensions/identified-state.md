---
title: 特定された状態
description: ステッチの認識を決定するフラグ。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 46%
---
# 特定された状態

「識別済み状態」 [&#x200B; ディメンション &#x200B;](overview.md)は、[&#x200B; クロスデバイス分析](../cda/overview.md)仮想レポートスイートに固有です。 レポートの実行時点で、ヒットがシステムによって識別（ステッチ）されているかどうかをレポートします。 このディメンションは、CDA によるデータのステッチ（「圧縮」）の精度を理解するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、各ヒットがユーザーにステッチされたかどうかに基づいて、レポートの実行時に[&#x200B; クロスデバイス分析](../cda/overview.md)によって計算されます。 クロスデバイス分析が仮想レポートスイート用に設定されている限り、設定する変数はありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（クロスデバイス分析で計算） |
| **Web SDK / XDM フィールド** | なし（クロスデバイス分析で計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、`"Identified"` および `"Unidentified"` が含まれます。

* **`"Identified"`**：ヒットが個人にマッピングされます。
* **`"Unidentified"`**：ヒットは個人にマッピングされず、どのアトリビューションメソッドでもマッピングできませんでした。
