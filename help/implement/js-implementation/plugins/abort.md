---
description: abort フラグを doPlugins 内に設定すると、トラッキング呼び出しは送信されません。
keywords: Analytics Implementation
title: s.abort フラグ
topic: Developer and implementation
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# s.abort フラグ

abort フラグを doPlugins 内に設定すると、トラッキング呼び出しは送信されません。

abort フラグはあらゆるトラッキング呼び出しによってリセットされるので、後続のトラッキング呼び出しも中止する必要がある場合は、このフラグを再度 doPlugins 内に設定する必要があります。

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

これにより、追跡したくないアクティビティ（ディスプレイ広告内の一部のカスタムリンクや外部リンクなど）の識別に使用するロジックを一元管理することができます。
