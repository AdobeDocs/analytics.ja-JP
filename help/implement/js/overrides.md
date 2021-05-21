---
title: 変数のオーバーライド
description: 変数のオーバーライドを使用して、一度のみのトラッキングまたはリンクトラッキングのための変数値をセットできます。
exl-id: e297ef94-c5f7-42b1-a9d0-57e073f0d1a9
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '106'
ht-degree: 100%

---

# 変数のオーバーライド

変数のオーバーライドを使用すると、ページ上の既存の変数に影響を与えることなく、単一のヒットに対する Analytics の値を変更できます。

## ワークフロー

1. 新しい JavaScript オブジェクトを作成します。オブジェクト名には任意の名前を指定できます。

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

オーバーライドパラメーターでオブジェクトを受け取ったトラッキングコールは、オーバーライドオブジェクトのすべての有効な値によって標準 Analytics オブジェクトの値を上書きします。既存の Analytics オブジェクトで既に定義されている変数は影響を受けません。
