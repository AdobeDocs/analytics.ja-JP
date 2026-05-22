---
title: 変数のオーバーライド
description: 変数のオーバーライドを使用して、一度のみのトラッキングまたはリンクトラッキングのための変数値をセットできます。
feature: Implementation Basics
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
role: Developer
TQID: 'https://experienceleague.adobe.com/IVA-JMaZPrKpF1NhhL6o3uiCQOOCtZerk78aQTqJAyc'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 106
ht-degree: 100%

---

# 変数のオーバーライド

変数のオーバーライドを使用すると、ページ上の既存の変数に影響を与えることなく、単一のヒットに対する Analytics の値を変更できます。

## ワークフロー

1. 新しい JavaScript オブジェクトを作成します。 オブジェクト名には任意の名前を指定できます。

   ```js
   var y = new Object();
   ```

2. このオブジェクトに有効な Analytics プロパティを割り当てます。

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. 適切なトラッキングコール内で、オブジェクトを引数として使用します。

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

オーバーライドパラメーターでオブジェクトを受け取ったトラッキングコールは、オーバーライドオブジェクトのすべての有効な値によって標準 Analytics オブジェクトの値を上書きします。 既存の Analytics オブジェクトで既に定義されている変数は影響を受けません。
