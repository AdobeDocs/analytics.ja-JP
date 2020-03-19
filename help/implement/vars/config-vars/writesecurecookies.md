---
title: writeSecureCookies
description: AppMeasurementがSecure属性を使用してcookieを設定することを許可します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# writeSecureCookies

この変 `writeSecureCookies` 数を使用すると、AppMeasurementでAnalyticsの [Secure cookieを設定できます](https://en.wikipedia.org/wiki/Secure_cookie) 。 この設定は、AppMeasurementによって設定された訪問者ID cookieと、この方法を使用して設定したCookieの両方に適用さ `Util.CookieWrite()` れます。 AppMeasurement 2.18.0以降が必要です。

> [!IMPORTANT] この変数を有効にする場 `writeSecureCookies` 合は、サイト上のすべてのコンテンツがHTTPS経由で安全に提供されていることを確認してください。 この変数が有効で、ページ上に安全でないコンテンツがある場合、AppMeasurementは機能しません。

## Adobe Experience Platformの起動でのセキュアCookieの書き込み

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.writeSecureCookiesとカスタムコードエディターの起動

この変 `s.writeSecureCookies` 数は、Cookieの作成時にAppMeasurementがセキュア属性を設定するかどうかを決定するブール値です。 Its default value is `false`. サイト上のすべてのコ `true` ンテンツがセキュリティで保護されており、AppMeasurementで設定されたcookieにセキュリティで保護された属性を持たせる場合は、この変数をに設定します。

```js
s.writeSecureCookies = true;
```
