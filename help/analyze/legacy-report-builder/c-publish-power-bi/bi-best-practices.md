---
description: Power BI のベストプラクティス。
title: ベストプラクティス
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
TQID: https://experienceleague.adobe.com/WXvRDft1TRz5qM9R8Psz-Yp2qY-AL-SrrXgXWRx55N0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 31%

---

# ベストプラクティス

{{legacy-arb}}

## Power BI ビジュアライゼーションの参照の保持

リクエストを作成すると、そのリクエストはPower BIで常に同じ参照になります。 ただし、リクエストを削除すると、同じディメンションに対して作成した新しいリクエストで参照が使用されます。

ワークブック内のリクエストを削除する場合は、Power BI でそのリクエストを参照しているビジュアライゼーションがないことを確認してください。そうでない場合にリクエストを削除すると、ビジュアライゼーションが機能しなくなるからです。

* 可能な限り、Report Builderで作成したリクエストを削除しないでください
* Report Builderでリクエストを削除する場合は、Power BIで対応するビジュアライゼーションも削除してください。
* 確信がない場合：不要になったリクエストを削除してから再公開し、Power BIに移動して、破損したビジュアライゼーションを確認します
