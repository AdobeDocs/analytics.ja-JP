---
title: Activity Map 地域別リンク
description: リンクと地域の連結された値。
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
TQID: https://experienceleague.adobe.com/xvYVA064hA0rsBdnLpxXllq3PD0zYAikFRjc6xNErvg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 151
ht-degree: 11%

---

# Activity Map 地域別リンク

「Activity Map Link By Region」 [&#x200B; ディメンション &#x200B;](overview.md)には、[Activity Map Link](activity-map-link.md)と[Activity Map Region](activity-map-link-by-region.md)の連結が表示されます。 このディメンションは、サイトの様々な地域に同じ名前のリンクが存在する場合に便利です。 例えば、ホームページへのリンクがすべて「ホーム」というラベルが付いている場合、このディメンションを使用して、各サイト地域のリンクを区別できます。

## このディメンションへのデータ入力

このディメンションは、[&#x200B; コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`および`c.a.activitymap.region`からデータを取得します。 これら2つの値は連結され、パイプ （`|`）で区切られます。 実装で[Activity Map](/help/analyze/activity-map/overview.md)を使用している場合、リンクがクリックされると、これらのコンテキストデータ変数によってデータが自動的に収集されます。

## ディメンション項目

Dimension項目には、[Activity Map Link](activity-map-link.md)および[Activity Map Region](activity-map-link-by-region.md)の値が含まれます。 組織のサイト構造と実装によって、収集された値が正確に決まります。
