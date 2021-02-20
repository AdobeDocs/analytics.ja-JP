---
title: Util.cookieWrite
description: Cookie に値を書き込みます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 100%

---


# Util.cookieWrite

Cookie は、同じドメインの複数のページにわたって情報を保存および取得できます。`Util.cookieWrite()` メソッドを使用して、Cookie に値を設定します。[`Util.cookieRead()`](util-cookieread.md) メソッドを使用すると、`Util.cookieWrite()` を使用して値セットを取得できます。

## Adobe Experience Platform Launch での Cookie の設定

Launch インターフェイスでは Cookie を設定する機能は提供されていません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.Util.cookieWrite()

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
