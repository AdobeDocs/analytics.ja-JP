---
description: 変数のオーバーライドを使用して、一度のみのトラッキングまたはリンクトラッキングのための変数値をセットできます。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 変数のオーバーライド
topic: Developer and implementation
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

