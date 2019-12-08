---
description: cookie に値を書き込みます。
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieWrite

cookie に値を書き込みます。

**構文：**

```
s.Util.cookieWrite(key, value [,expire])
```

**パラメーター:**

| パラメーター | 説明 |
|---|---|
| key | （必須）cookie で値を書き込むためのキー。 |
| value | （オプション）cookie に書き込むための値。 |
| expire | （オプション）cookie の有効期限を含む日付オブジェクト。デフォルトでは、セッション cookie を使用します。 |

**戻り値:**

**例：**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

