---
description: Power BI のベストプラクティス。
title: ベストプラクティス
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

---

# ベストプラクティス

{{legacy-arb}}

## Power BI ビジュアライゼーションの参照の保持

リクエストを作成すると、そのリクエストは Power BI で常に同じ参照を持ちます。ただし、リクエストを削除すると、その参照は、同じディメンションに関して作成した新しいリクエストによって使用されます。

ワークブック内のリクエストを削除する場合は、Power BI でそのリクエストを参照しているビジュアライゼーションがないことを確認してください。そうでない場合にリクエストを削除すると、ビジュアライゼーションが機能しなくなるからです。

* 可能であれば、Report Builder で作成したリクエストは削除しないでください。
* Report Builder でリクエストを削除する場合は、Power BI の対応するビジュアライゼーションも削除するようにしてください。
* 対応するビジュアライゼーションかわからない場合は、不要になったリクエストを削除し、再発行して Power BI に移動し、壊れているビジュアライゼーションを確認します。
