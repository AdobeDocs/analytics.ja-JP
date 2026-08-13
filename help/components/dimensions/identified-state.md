---
title: 特定された状態
description: ステッチの認識を決定するフラグ。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 111
ht-degree: 82%

---

# 特定された状態

「識別済み状態」 [&#x200B; ディメンション &#x200B;](overview.md)は、[&#x200B; クロスデバイス分析](../cda/overview.md)仮想レポートスイートに固有です。 レポートの実行時点で、ヒットがシステムによって識別（ステッチ）されているかどうかをレポートします。 このディメンションは、CDA によるデータのステッチ（「圧縮」）の精度を理解するのに役立ちます。

## このディメンションへのデータ入力

仮想レポートスイート用に[クロスデバイス分析](../cda/overview.md)が設定されている限り、このディメンションは初期設定のままで機能します。

## ディメンション項目

ディメンション項目には、`"Identified"` および `"Unidentified"` が含まれます。

* **`"Identified"`**：ヒットが個人にマッピングされます。
* **`"Unidentified"`**：ヒットは個人にマッピングされず、どのアトリビューションメソッドでもマッピングできませんでした。
