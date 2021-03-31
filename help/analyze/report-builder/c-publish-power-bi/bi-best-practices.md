---
description: Power BIのベストプラクティス。
title: ベストプラクティス
uuid: 6d55a9aa-030e-4e4d-963c-ec9cc38e1731
feature: Report Builder
role: 営業者、管理者
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 95%

---


# ベストプラクティス

## Power BI ビジュアライゼーションの参照の保持 {#section_7ED14FE64D974681A57EB91EF1B47CB6}

リクエストを作成すると、そのリクエストは Power BI で常に同じ参照を持ちます。ただし、リクエストを削除すると、その参照は、同じディメンションに関して作成した新しいリクエストによって使用されます。

ワークブック内のリクエストを削除する場合、Power BI でそのリクエストを参照しているビジュアライゼーションがないことを確認してください。これは、参照されているリクエストを削除すると、ビジュアライゼーションが壊れてしまうからです。

* 可能であれば、Report Builder で作成したリクエストは削除しないでください。
* Report Builder でリクエストを削除する場合は、Power BI の対応するビジュアライゼーションも削除するようにしてください。
* 対応するビジュアライゼーションかわからない場合は、不要になったリクエストを削除し、再発行して Power BI に移動し、壊れているビジュアライゼーションを確認します。

