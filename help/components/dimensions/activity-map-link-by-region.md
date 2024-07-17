---
title: Activity Map 地域別リンク
description: リンクと地域を連結した値。
feature: Dimensions
role: User, Admin
source-git-commit: 65e75a1c2b39823e72abfb0e5b61122c62f1f013
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# Activity Map 地域別リンク

「Activity Mapリンク （地域別）」 [ ディメンション ](overview.md) には、[Activity Mapリンク ](activity-map-link.md) と [Activity Map地域 ](activity-map-link-by-region.md) の連結が表示されます。 このディメンションは、同じ名前のリンクがサイトの異なる地域に存在する場合に役立ちます。 例えば、ホームページへの複数のリンクがすべて「ホーム」というラベルになっている場合、このディメンションを使用して、各サイト地域のそれらのリンクを区別できます。

## このディメンションへのデータ入力

このディメンションは、[ コンテキストデータ変数 ](/help/implement/vars/page-vars/contextdata.md)`c.a.activitymap.link` および `c.a.activitymap.region` からデータを取得します。 これら 2 つの値は連結され、パイプ（`|`）で区切られます。 実装で [Activity Map](/help/analyze/activity-map/overview.md) を使用している場合、リンクがクリックされると、これらのコンテキストデータ変数によってデータが自動的に収集されます。

## ディメンション項目

Dimension項目には、[Activity Mapリンク ](activity-map-link.md) および [Activity Map地域 ](activity-map-link-by-region.md) の値が含まれます。 組織のサイト構造と実装によって、収集される正確な値が決まります。
