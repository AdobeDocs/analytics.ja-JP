---
title: ページが見つかりません（指標）
description: エラーを含むヒットの数。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
TQID: https://experienceleague.adobe.com/V5jVT8wh71qMrchQmmM6c4EMofHPUEI388TmAf7Zf6M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 87%

---

# ページが見つかりません

*このヘルプページでは、「ページが見つかりません」が指標として機能する方法を説明します。 ディメンションとして機能する方法について詳しくは、[ ページが見つかりません](../dimensions/pages-not-found.md) ディメンション ページを参照してください。*

「ページが見つかりません」 [ 指標 ](overview.md) は、訪問者がエラーに遭遇した時点でディメンションが設定または持続されたヒット数を示します。 この指標は、エラーメッセージ（404 など）を含んだページや URL を確認する場合に役立ちます。 その後、この情報を web 開発チームに渡し、チームはエラーの原因を特定して修正できます。

## この指標の計算方法

この指標では、[`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数が `"errorPage"` の値と等しいすべてのヒットをカウントします。 これは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションと同じ指標です。
