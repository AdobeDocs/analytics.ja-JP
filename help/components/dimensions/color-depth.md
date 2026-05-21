---
title: 色深度
description: デバイスの色深度。
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 94%

---

# 色深度

「色深度」 [&#x200B; ディメンション &#x200B;](overview.md)は、デバイスがサポートする色数をレポートします。 このディメンションは、1600 万色をサポートしていないデバイスから発生するトラフィックの量を調べるのに役立ちます。 これまで、このレポートは新しいモバイル Web が登場したときに役に立ちました。ただし、現在の世代のほとんどのデバイスは 1600 万色をサポートしています（0 ～ 255 は赤、緑、青）。 <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## このディメンションへのデータ入力

このディメンションは、ルックアップテーブルを参照し、ビット値をより読みやすい形式に変換します。 イメージリクエスト内の [`c` クエリ文字列](/help/implement/validate/query-parameters.md)を収集します。 AppMeasurement は、`screen.colorDepth` 変数を使用して、イメージリクエストクエリ文字列を設定します。 AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement 以外のデータ収集方式（API 経由など）を使用する場合は、各ヒットに `c` クエリ文字列パラメーターを有効なビット値で含めてください。

## ディメンション項目

ディメンション項目には、デバイスでサポートされる色の数が含まれます。 例えば、`"16 million (24-bit)"`、`"16 million (32-bit)"`、`"65,536 (16-bit)"` などの値があります。 AppMeasurement が色深度を判断できない場合は、`"None"` と表示されます。

>[!TIP]
>
>24 ビットと 32 ビットのサポートの違いは、32 ビットがアルファチャンネル（RGBA）をサポートするのに対し、24 ビットがサポートしない（RGB）ことです。 この概念について詳しくは、Wikipedia の[色深度](https://ja.wikipedia.org/wiki/色深度)を参照してください。
