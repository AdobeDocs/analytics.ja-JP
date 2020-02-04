---
title: 変数のオーバーライド
description: 変数のオーバーライドを使用して、一度のみのトラッキングまたはリンクトラッキングのための変数値をセットできます。
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# 変数のオーバーライド

変数の上書きを使用すると、ページ上の既存の変数に影響を与えることなく、単一のヒットに対するAnalyticsの値を変更できます。

## ワークフロー

1. 新しいJavaScriptオブジェクトを作成します。 オブジェクト名は任意の名前を指定できます。

   ```js
   var y = new Object();
   ```

2. 有効なAnalyticsプロパティをこのオブジェクトに割り当てる：

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

overridesパラメーターでオブジェクトを受け取ったトラッキングコールは、overrideオブジェクトの有効なすべての値によって標準Analyticsオブジェクトの値を上書きします。 既存のAnalyticsオブジェクトで既に定義されている変数は影響を受けません。
