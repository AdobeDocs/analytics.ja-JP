---
description: 新しい訪問が開始しているかを確認します。
keywords: Analytics の導入
seo-description: 新しい訪問が開始しているかを確認します。
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: 開発者と導入
uuid: 7dd3e51f-2f73-4452- a9fb- cac513cd28eb
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

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

