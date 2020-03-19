---
title: Util.cookieWrite
description: cookieの値を書き込みます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieWrite

cookieは、同じドメインの複数のページにわたって情報を保存および取得できます。 このメソッド `Util.cookieWrite()` を使用して、cookieに値を設定します。 このメソッドを使用し [`Util.cookieRead()`](util-cookieread.md) て、を使用して値セットを取得できま `Util.cookieWrite()`す。

## Adobe Experience Platform Launchでのcookieの設定

Launchは、インターフェイスにcookieを設定する機能を提供しません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.Util.cookieWrite()とカスタムコードエディターの起動

このメソッド `s.Util.cookieWrite()` を呼び出して、cookieに目的の値を設定します。

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

cookieの有効期限を決定する3つ目のオプションの引数を使用できます。 を使用して設定され `s.Util.cookieWrite()` たcookieは、デフォルトでブラウザーセッションの終了時に期限切れになります。

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## 例

cookieの書き込みが成功した場合に変数をインスタンス化できます。 この変数はブール値です。

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
