---
description: リクエストを削除してワークブックを編集し、新しいリクエストの領域を確保する方法を説明します。
title: 出力マッピングの削除方法
uuid: a6805800-4cb9-4ccc-aada-198a15def643
feature: Report Builder
role: User, Admin
exl-id: 88afef3b-1559-453b-a8e2-7251ef8c82ec
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 83%

---

# 出力マッピングの削除

{{legacy-arb}}

ワークブック編集中に新しいリクエストの領域を確保したい場合、既存リクエストの削除が必要になることがあります。

領域を確保するには、セルにマッピングされているリクエストを削除する必要があります。リクエストを含む行や列を削除してしまうと、関連するリクエストの有効性が失われます（その結果、更新が失敗します）。Excel メニューの&#x200B;**[!UICONTROL 編集]**／**[!UICONTROL 数式と値のクリア]**&#x200B;を選択すると、セル内に表示されている値は削除されますが、マッピングは残るので、「更新」すると値が復活します。

スプレッドシートのセル内にある特定のマッピングを削除するには、その行、列または指標項目を右クリックし、「**[!UICONTROL リクエストの削除]**」を選択します。