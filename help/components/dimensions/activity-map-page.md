---
title: Activity Map ページ
description: リンクがクリックされたときのページ名。
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
TQID: https://experienceleague.adobe.com/WJ0uk-LqIABwehzzy79c2o1cd3EvI-AKUJ--vmLnKRE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 6%

---

# Activity Map ページ

「Activity Map Page」 [ ディメンション ](overview.md)には、リンクがクリックされたときに訪問者がアクセスしたページが表示されます。 このディメンションを使用すると、最もクリックされたリンクを含むページを特定できます。 このディメンションは、Activity Map オーバーレイでも使用され、表示するリンクを決定します。

## このディメンションへのデータ入力

このディメンションは、[ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`からデータを取得します。 実装で[Activity Map](/help/analyze/activity-map/overview.md)を使用している場合、このコンテキストデータ変数は、リンクがクリックされたときにデータを自動的に収集します。

クリックされた特定のリンクについて、このコンテキストデータ変数は[ ページ ](page.md) ディメンションの値を収集します。 ページディメンションに値が含まれていない場合は、[ ページ URL](page-url.md) ディメンションが代わりに使用されます（ページディメンションが使用するフォールバックと同様）。 Activity Map データは、通常、リンクをクリックした後の次のヒットに送信されます。 このディメンションを使用すると、データ送信時のページ値ではなく、リンクがクリックされたときのページ値を判断できます。

## ディメンション項目

Dimension項目には、[Page](page.md) ディメンションに見つかったすべての値が含まれます。
