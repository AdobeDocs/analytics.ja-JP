---
title: Util.cookieWrite
description: Cookie に値を書き込みます。
feature: Variables
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '131'
ht-degree: 100%

---

# Util.cookieWrite

Cookie は、同じドメインの複数のページにわたって情報を保存および取得できます。`Util.cookieWrite()` メソッドを使用して、Cookie に値を設定します。[`Util.cookieRead()`](util-cookieread.md) メソッドを使用すると、`Util.cookieWrite()` を使用して値セットを取得できます。

## Adobe Experience Platform のタグを使用した Cookie の設定

データ収集 UI には、インターフェイスで Cookie を設定する機能はありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.Util.cookieWrite()

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
