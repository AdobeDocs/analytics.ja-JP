---
description: クリックされたリンク名。
title: Activity Map リンク
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
TQID: https://experienceleague.adobe.com/A5HaPb0TghRKVykJ9V2UMJ0mlsYElLkCyBwxzTd6VII
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 8%

---

# Activity Map リンク

「Activity Map リンク」 [ ディメンション ](overview.md)には、クリックされた最も人気のあるリンクが表示されます。 このディメンションを使用すると、リンクがクリックされた場所に関係なく、サイト上のどのリンクが最も使用されているかを比較できます。

## このディメンションへのデータ入力

このディメンションは、[ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`からデータを取得します。 実装で[Activity Map](/help/analyze/activity-map/overview.md)を使用している場合、このコンテキストデータ変数は、リンクがクリックされたときにデータを自動的に収集します。

クリックされた特定のリンクに対して、Activity Mapは次の（順番に）検索します。

1. `s_objectID`変数
1. リンクの内部テキスト
1. 画像の`alt`属性
1. `title`属性
1. 画像の`src`属性
1. フォームの`action`属性

クリックされた要素に上記の条件のいずれも含まれていない場合、Activity Mapはそのクリックのデータを収集しません。

## ディメンション項目

Dimensionの項目には、訪問者がクリックするリンクテキストまたはその他のリンク属性が含まれます。 組織のサイト構造と実装によって、収集された値が正確に決まります。
