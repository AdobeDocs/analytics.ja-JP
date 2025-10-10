---
title: Activity Map 地域別リンク
description: リンクと地域を連結した値。
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# Activity Map 地域別リンク

「Activity Map リンク （地域別）」 [&#x200B; ディメンション &#x200B;](overview.md) には、[Activity Map リンク &#x200B;](activity-map-link.md) と [Activity Map リージョン &#x200B;](activity-map-link-by-region.md) の連結が表示されます。 このディメンションは、同じ名前のリンクがサイトの異なる地域に存在する場合に役立ちます。 例えば、ホームページへの複数のリンクがすべて「ホーム」というラベルになっている場合、このディメンションを使用して、各サイト地域のそれらのリンクを区別できます。

## このディメンションへのデータ入力

このディメンションは、[&#x200B; コンテキストデータ変数 &#x200B;](/help/implement/vars/page-vars/contextdata.md)`c.a.activitymap.link` および `c.a.activitymap.region` からデータを取得します。 これら 2 つの値は連結され、パイプ（`|`）で区切られます。 実装で [Activity Map](/help/analyze/activity-map/overview.md) を使用している場合、リンクがクリックされると、これらのコンテキストデータ変数によって自動的にデータが収集されます。

## ディメンション項目

Dimension項目には、[Activity Map リンク &#x200B;](activity-map-link.md) および [Activity Map リージョン &#x200B;](activity-map-link-by-region.md) の値が含まれます。 組織のサイト構造と実装によって、収集される正確な値が決まります。
