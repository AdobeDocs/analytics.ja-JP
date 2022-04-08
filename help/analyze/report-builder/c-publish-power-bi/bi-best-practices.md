---
description: Power BI のベストプラクティス。
title: ベストプラクティス
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: ht
source-wordcount: '138'
ht-degree: 100%

---

# ベストプラクティス

## Power BI ビジュアライゼーションの参照の保持 {#section_7ED14FE64D974681A57EB91EF1B47CB6}

リクエストを作成すると、そのリクエストは Power BI で常に同じ参照を持ちます。ただし、リクエストを削除すると、その参照は、同じディメンションに関して作成した新しいリクエストによって使用されます。

ワークブック内のリクエストを削除する場合、Power BI でそのリクエストを参照しているビジュアライゼーションがないことを確認してください。これは、参照されているリクエストを削除すると、ビジュアライゼーションが壊れてしまうからです。

* 可能であれば、Report Builder で作成したリクエストは削除しないでください。
* Report Builder でリクエストを削除する場合は、Power BI の対応するビジュアライゼーションも削除するようにしてください。
* 対応するビジュアライゼーションかわからない場合は、不要になったリクエストを削除し、再発行して Power BI に移動し、壊れているビジュアライゼーションを確認します。
