---
description: リクエストウィザード：ステップ 1 では、データリクエストに精度を適用できます。 「粒度」では、レポートに含まれる時間ベースの詳細レベルを指定します。
title: 精度
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
TQID: https://experienceleague.adobe.com/26j4Fernl4bfuYeyuVVzw1K5hZvNSD6pDUVOfEc0J8s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 14%

---

# 精度

{{legacy-arb}}

リクエストウィザード：手順1では、データリクエストに詳細レベルを適用できます。 「粒度」では、レポートに含まれる時間ベースの詳細レベルを指定します。

有効な値は、時間、日、週、月、四半期、年、集計です。

## Report Builder での精度の処理方法

[!UICONTROL 月]の精度を持つ1か月の日付範囲を選択するとします。 リクエストには、正確に1か月分のデータに基づく指標の合計が表示されます。 リクエストの日付範囲が1四半期に及ぶ場合、レポートには3つの数値が表示されます。各月の単位ごとに1つ、またはその一部です。 今日が3月18日の場合、前四半期を選択すると、1月1日から1月31日の1つの数値、2月1日から2月28日の別の数値、および3月1日から3月17日の最終数値が返されます。
