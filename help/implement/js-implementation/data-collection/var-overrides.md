---
description: 変数のオーバーライドを使用して、一度のみのトラッキングまたはリンクトラッキングのための変数値をセットできます。
keywords: Analytics Implementation
subtopic: Variables
title: 変数のオーバーライド
topic: Developer and implementation
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 変数のオーバーライド

変数のオーバーライドを使用して、一度のみのトラッキングまたはリンクトラッキングのための変数値をセットできます。

変数をオーバーライドするには、新しいオブジェクトを作成し、変数値を割り当て、このオブジェクトを最初のパラメーターとして `s.t()` に、または 4 番目のパラメーターとして `s.tl()` に渡します。

```js
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
  
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
  
s.t(overrides);  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

```js
s.linkTrackVars="eVar1,eVar2,eVar3,events"; 
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
 
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
 
s.tl(this,'e','AnotherSite',overrides,'navigate')  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

