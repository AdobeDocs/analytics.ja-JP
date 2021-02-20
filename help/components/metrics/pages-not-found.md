---
title: エラーページ（404）
description: エラーを含むヒットの数。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%

---


# エラーページ（404）

*このヘルプページでは、「ページが見つかりません」が指標として機能する方法を説明します。詳しくは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションを参照してください。*

「ページが見つかりません」指標は、ページにエラーが含まれたヒットの数を示します。この指標は、エラーメッセージが含まれているページまたは URL（404 など）を確認したい場合に役立ちます。そのため、エラーの原因を特定し、修正できます。

## この指標の計算方法

この指標では、[`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数が `"errorPage"` の値と等しいすべてのヒットをカウントします。これは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションと同じ指標です。