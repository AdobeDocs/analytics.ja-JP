---
title: エラーページ（指標）
description: エラーを含むヒットの数。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 45%

---

# エラーページ（404）

*このヘルプページでは、「ページが見つかりません」が指標として機能する方法を説明します。詳しくは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションを参照してください。*

「エラーページ (404)」 [指標](overview.md) 訪問者がエラーに遭遇した時点でのディメンションが設定または持続されたヒット数を示します。 この指標は、エラーメッセージが含まれているページや URL（404 など）を確認する場合に役立ちます。 その後、この情報を Web 開発チームに渡し、Web 開発チームがエラーの原因を特定して修正できます。

## この指標の計算方法

この指標では、[`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数が `"errorPage"` の値と等しいすべてのヒットをカウントします。これは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションと同じ指標です。
