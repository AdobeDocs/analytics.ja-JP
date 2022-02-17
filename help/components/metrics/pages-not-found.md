---
title: エラーページ（404）
description: エラーを含むヒットの数。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%

---

# エラーページ（404）

*このヘルプページでは、「ページが見つかりません」が指標として機能する方法を説明します。詳しくは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションを参照してください。*

「ページが見つかりません」指標は、ページにエラーが含まれたヒットの数を示します。この指標は、エラーメッセージが含まれているページまたは URL（404 など）を確認したい場合に役立ちます。そのため、エラーの原因を特定し、修正できます。

## この指標の計算方法

この指標では、[`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数が `"errorPage"` の値と等しいすべてのヒットをカウントします。これは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションと同じ指標です。
