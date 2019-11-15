---
description: 新しい訪問が開始しているかを確認します。
keywords: Analytics Implementation
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getVisitStart

新しい訪問が開始しているかを確認します。

**設定変数**

なし

**パラメーター**

c = (文字列) トラッキングのための cookie の名前。

**戻り値**

（整数値）訪問の最初のページは 1、それ以外は 0。

**サンプル呼び出し**

```
s.eVar50 = s.getVisitStart("s_visit");
```

