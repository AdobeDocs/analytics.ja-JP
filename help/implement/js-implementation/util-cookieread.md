---
description: cookie の値を取得します。
keywords: Analytics Implementation
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

