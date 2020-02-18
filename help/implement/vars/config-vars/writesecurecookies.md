---
title: writeSecureCookies
description: AppMeasurementがセキュア属性を持つcookieを設定することを許可します。
translation-type: tm+mt
source-git-commit: 117a3c1ad411b25d8277b5678915b76eadd232a7

---


# writeSecureCookies

この変 `writeSecureCookies` 数を使用すると、AppMeasurementでAnalytics用のセキュ [アcookie](https://en.wikipedia.org/wiki/Secure_cookie) を設定できます。 この設定は、AppMeasurementによって設定された訪問者ID cookieと、このメソッドを使用して設定したcookieの両方に適用さ `Util.CookieWrite` れます。 AppMeasurement 2.18.0以降が必要です。

> [!NOTE] この変数を有効にする場 `writeSecureCookies` 合は、サイト上のすべてのコンテンツがHTTPS経由で安全に提供されていることを確認してください。

## Adobe Experience Platformの起動でのセキュアcookieの書き込み

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.writeSecureCookiesおよびカスタムコードエディターの起動

この変 `s.writeSecureCookies` 数は、Cookieの作成時にAppMeasurementがセキュア属性を設定するかどうかを決定するブール値です。 Its default value is `false`. サイト上のすべてのコ `true` ンテンツがセキュリティで保護されており、AppMeasurementによって設定されたcookieにセキュリティで保護された属性を設定する場合は、この変数をに設定します。

```js
s.writeSecureCookies = true;
```
