---
description: 変数のオーバーライドを使用して、一度のみのトラッキングまたはリンクトラッキングのための変数値をセットできます。
keywords: Analytics の実装
seo-description: 変数のオーバーライドを使用して、一度のみのトラッキングまたはリンクトラッキングのための変数値をセットできます。
seo-title: 変数のオーバーライド
solution: Analytics
subtopic: 変数
title: 変数のオーバーライド
topic: 開発者と実装
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

