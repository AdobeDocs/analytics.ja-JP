---
title: 色深度
description: デバイスの色深度。
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%
---
# 色深度

「色深度」 [ ディメンション ](overview.md)は、デバイスがサポートする色数をレポートします。 このディメンションは、1600 万色をサポートしていないデバイスから発生するトラフィックの量を調べるのに役立ちます。 これまで、このレポートは新しいモバイル Web が登場したときに役に立ちました。ただし、現在の世代のほとんどのデバイスは 1600 万色をサポートしています（0 ～ 255 は赤、緑、青）。 <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## このディメンションへのデータ入力

ブラウザーの`screen.colorDepth` プロパティから、クライアント側で色深度が自動的に収集されます。Adobeは、ルックアップテーブルを通じて読み取り可能なフォーマットに変換します。 AppMeasurementまたはWeb SDK（タグ）の実装では、設定することのできない機能です。 AppMeasurementまたはWeb SDK以外（API経由など）でデータを収集する場合は、各ヒットに有効なビット値を送信します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（自動収集） |
| **Web SDK / XDM フィールド** | なし（自動収集） |
| **クエリパラメーター** | [`c`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<colorDepth>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 20 バイト |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、デバイスでサポートされる色の数が含まれます。 例えば、`"16 million (24-bit)"`、`"16 million (32-bit)"`、`"65,536 (16-bit)"` などの値があります。 AppMeasurement が色深度を判断できない場合は、`"None"` と表示されます。

>[!TIP]
>
>24 ビットと 32 ビットのサポートの違いは、32 ビットがアルファチャンネル（RGBA）をサポートするのに対し、24 ビットではサポートされない（RGB）ことです。 この概念について詳しくは、Wikipedia の[色深度](https://ja.wikipedia.org/wiki/色深度)を参照してください。
