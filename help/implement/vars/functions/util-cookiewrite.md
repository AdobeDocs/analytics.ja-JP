---
title: Util.cookieWrite
description: Cookie に値を書き込みます。
feature: Appmeasurement Implementation
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 70%

---

# Util.cookieWrite

Cookie は、同じドメインの複数のページにわたって情報を保存および取得できます。`Util.cookieWrite()` メソッドを使用して、Cookie に値を設定します。[`Util.cookieRead()`](util-cookieread.md) メソッドを使用すると、`Util.cookieWrite()` を使用して値セットを取得できます。

## Adobe Analytics拡張機能と Web SDK拡張機能を使用して cookie を設定します

Adobe Experience Platform Data Collection には、インターフェイスで cookie を設定する機能はありません。

## AppMeasurementの s.Util.cookieWrite （）と Analytics 拡張機能のカスタムコードエディター

`s.Util.cookieWrite()` メソッドを呼び出して、Cookie に目的の値を設定します。

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

Cookie の有効期限を決定するには 3 番目のオプション引数を使用できます。`s.Util.cookieWrite()` を使用して設定された Cookie は、デフォルトでブラウザーセッションの終了時に期限切れになります。

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## 例

Cookie の書き込みが成功した場合は、変数をインスタンス化できます。この変数はブール値です。

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
