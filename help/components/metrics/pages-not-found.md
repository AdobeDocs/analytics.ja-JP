---
title: エラーページ（指標）
description: エラーを含むヒットの数。
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# エラーページ（404）

*このヘルプページでは、「ページが見つかりません」が指標として機能する方法を説明します。詳しくは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションを参照してください。*

「ページが見つかりません」指標は、ページにエラーが含まれたヒットの数を示します。この指標は、エラーメッセージが含まれているページまたは URL（404 など）を確認したい場合に役立ちます。そのため、エラーの原因を特定し、修正できます。

* この指標の計算方法[](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)
* この指標では、[`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数が `"errorPage"` の値と等しいすべてのヒットをカウントします。これは、「[ページが見つかりません](../dimensions/pages-not-found.md)」ディメンションと同じ指標です。](referrer.md)

## Populate this dimension with data

This dimension retrieves data from the [`pageType` and `g` query strings](/help/implement/validate/query-parameters.md) in image requests. If the `pageType` query string equals `errorPage`, the `g` query string (page URL) is recorded. AppMeasurement collects this data using the [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable. If the `pageType` variable is not defined or set to anything other than `errorPage`, no data for this dimension is collected.

## Dimension items

Dimension items include the URLs of pages on your site where an error occurred.
