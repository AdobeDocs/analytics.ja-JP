---
description: cookie の値を取得します。
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieRead

cookie の値を取得します。

**構文：**

```
s.Util.cookieRead(key)
```

**パラメーター:**

| パラメーター | 説明 |
|---|---|
| key | （必須）cookie で値を書き込むためのキー。 |

**戻り値:**

cookie の値（cookie が見つからない場合は空の文字列）を返します。

**例：**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

