---
description: Power BI のベストプラクティス。
title: ベストプラクティス
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 78%

---

# ベストプラクティス

## Power BI ビジュアライゼーションの参照の保持 {#section_7ED14FE64D974681A57EB91EF1B47CB6}

リクエストを作成すると、そのリクエストは Power BI で常に同じ参照を持ちます。ただし、リクエストを削除すると、その参照は、同じディメンションに関して作成した新しいリクエストによって使用されます。

ワークブック内のリクエストを削除する場合は、Power BI内のそのリクエストを指すビジュアライゼーションがないことを確認してください。ビジュアライゼーションがないと、ビジュアライゼーションが壊れるからです。

* 可能であれば、Report Builder で作成したリクエストは削除しないでください。
* Report Builder でリクエストを削除する場合は、Power BI の対応するビジュアライゼーションも削除するようにしてください。
* 対応するビジュアライゼーションかわからない場合は、不要になったリクエストを削除し、再発行して Power BI に移動し、壊れているビジュアライゼーションを確認します。
