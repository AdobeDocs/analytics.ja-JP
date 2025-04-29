---
title: ページが見つかりません（指標）
description: エラーを含むヒットの数。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 87%

---

# ページが見つかりません

*このヘルプページでは、「ページが見つかりません」が指標として機能する方法を説明します。ディメンションとしての動作について詳しくは、[ ページが見つかりません ](../dimensions/pages-not-found.md) ディメンションページを参照してください。*

「ページが見つかりません」 [ 指標 ](overview.md) は、訪問者がエラーに遭遇した時点でディメンションが設定または持続されたヒット数を示します。 この指標は、エラーメッセージ（404 など）を含んだページや URL を確認する場合に役立ちます。 その後、この情報を web 開発チームに渡し、チームはエラーの原因を特定して修正できます。

## この指標の計算方法

この指標では、[`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数が `"errorPage"` の値と等しいすべてのヒットをカウントします。これは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションと同じ指標です。
