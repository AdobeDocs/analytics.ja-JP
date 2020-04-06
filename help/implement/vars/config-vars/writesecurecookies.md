---
title: writeSecureCookies
description: AppMeasurementがSecure属性を使用してcookieを設定することを許可します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# writeSecureCookies

この変 `writeSecureCookies` 数を使用すると、AppMeasurementでAnalyticsの [Secure cookieを設定できます](https://en.wikipedia.org/wiki/Secure_cookie) 。 この設定は、AppMeasurementによって設定された訪問者ID cookieと、この方法を使用して設定したcookieの両方に適用さ `Util.CookieWrite()` れます。 AppMeasurement 2.18.0 以降が必要です。

>[!IMPORTANT] この変数を有効にする場 `writeSecureCookies` 合は、サイト上のすべてのコンテンツがHTTPS経由で安全に提供されていることを確認してください。 この変数が有効で、ページ上に安全でないコンテンツがある場合、AppMeasurementは機能しません。

## Adobe Experience Platformの起動でのセキュアCookieの書き込み

Launch には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムのコードエディターを使用します。

## AppMeasurementのs.writeSecureCookiesとカスタムコードエディターの起動

この変 `s.writeSecureCookies` 数は、Cookieの作成時にAppMeasurementがセキュア属性を設定するかどうかを決定するブール値です。 デフォルト値は `false` です。サイト上のすべてのコ `true` ンテンツがセキュリティで保護されており、AppMeasurementで設定されたcookieにセキュリティで保護された属性を持たせる場合は、この変数をに設定します。

```js
s.writeSecureCookies = true;
```
