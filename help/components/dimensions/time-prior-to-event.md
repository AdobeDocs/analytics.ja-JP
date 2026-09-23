---
title: イベント前の時間
description: 指標から訪問の最初のヒットまでの時間。
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
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
source-wordcount: '197'
ht-degree: 53%
---
# イベント前の時間

「イベント前の時間」ディメンション [1&rbrace;は、訪問の最初のヒットから目的の指標までの間に経過した時間をレポートします。 &#x200B;](overview.md)このディメンションは、フォームの送信や購入など、成功イベントに到達するまでの時間を判断するのに役立ちます。

## このディメンションへのデータ入力

Adobeは、訪問の最初のヒットからターゲットイベントまでの経過時間から、このディメンションをサーバーサイドで計算します。 設定する変数がありません。 すぐに利用できますが、カスタムイベントや購入イベントがサイトに実装されている場合に最適です。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、`"Less than 1 minute"` から `"More than 15 hours"` までの時間ベースのグループが含まれます。 例えば、最初のヒットから購入までに 23 分かかった訪問者は、`"10 to 30 minutes"` ディメンション項目の下に含まれます。 バケットは、この指標に対してカスタマイズできません。
