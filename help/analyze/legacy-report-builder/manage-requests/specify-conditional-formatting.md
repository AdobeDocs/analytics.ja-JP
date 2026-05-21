---
description: ワークブックのセルに条件付き書式を適用する方法を説明します。
title: ワークブックの条件付き書式設定について
uuid: 13ac12f1-3498-4bf9-a6d0-c5d84e0125dc
feature: Report Builder
role: User, Admin
exl-id: 5a5f2415-8269-4c8a-9193-784537b29edf
TQID: https://experienceleague.adobe.com/UnZqnq2Y3D7AfZ6mM0xNVVr4F-wOKhqix4tTTo6BQg0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 175
ht-degree: 7%

---

# 条件付き書式の指定

{{legacy-arb}}

埋め込みリクエストを含むレポートを作成した後で、ワークブックのセルに条件付き書式を適用できます。

Report Builder ツールバーで、**[!UICONTROL 書式]**&#x200B;をクリックします。

条件付き書式設定を使用すると、監視する結果または値を含むセルを識別できます。 例えば、収益が期待値を下回っている場合は赤の陰影または強調表示を特定のセルに適用し、収益が予測値を超えている場合は青の陰影を適用できます。 リクエストの日付範囲を変更すると、条件付き書式がセル値に適用される条件が削除される場合、その条件を強調表示する書式は一時的に無効になります。 条件が満たされないので、指定した条件付き書式が変更されない場合、条件付き書式は削除するまでセルに適用され続けます。

セキュリティ上の理由から、ExcelのVisual Basic for Applications （VBA）言語を使用してブックのマクロを記述する場合、マクロは無効になります。

>[!NOTE]
>
>条件付き書式設定はExcel機能です。 書式ルール作成については、Excel のマニュアルを参照してください。
