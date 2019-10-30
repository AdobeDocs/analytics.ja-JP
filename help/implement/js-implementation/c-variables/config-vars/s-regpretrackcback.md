---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.registerPreTrackCallback と s.registerPostTrackCallback

これらの関数は、コールバック（関数）およびそのパラメーターをパラメーターとして取ります。次に例を示します。

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

コールバックは、`requestUrl` およびコールバックの登録時に渡されたパラメーターとともに呼び出されます。コールバックの登録に使用されたメソッドにより、この呼び出しはトラッキングコールの前または後に発生します。

これらのコールバックが呼び出される順序は保証されていません。トラッキングコール前フックで登録されるコールバックは、最終トラッキング URL の作成後に呼び出されます。トラッキングコール後フックのコールバックは、トラッキングコールの成功後に呼び出されます（トラッキングコールが失敗すると、コールバックは呼び出されません）。`registerPreTrackCallback` で登録されたコールバックは、トラッキングコールには影響しません。また、登録されたコールバックでいずれかのトラッキングメソッドを呼び出すことは、無限ループの原因となるおそれがあるため、推奨されていません。
