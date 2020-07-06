---
title: writeSecureCookies
description: AppMeasurement が Secure 属性を持つ cookie を設定することを許可します。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 100%

---


# writeSecureCookies

この `writeSecureCookies` 変は、AppMeasurement が Analytics の [セキュリティで保護された cookie](https://en.wikipedia.org/wiki/Secure_cookie) を設定することを許可します。この設定は、AppMeasurement によって設定された訪問者 ID Cookie と、この `Util.CookieWrite()` メソッドを使用して設定した Cookie の両方に適用されます。AppMeasurement 2.18.0 以降が必要です。

>[!IMPORTANT]
>
> この `writeSecureCookies` 変数を有効にする場合は、サイト上のすべてのコンテンツが HTTPS 経由で安全に提供されていることを確認してください。この変数が有効になっており、ページに安全でないコンテンツが存在する場合、AppMeasurement は機能しません。

## Adobe Experience Platform Launch でのセキュア Cookie の書き込み

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.writeSecureCookies

この `s.writeSecureCookies` 変数は、AppMeasurement が cookie の作成時にセキュア属性を設定するかどうかを決定するブール値です。デフォルト値は `false` です。サイト上のすべてのコンテンツがセキュリティで保護されていて、AppMeasurement によって設定されるcookieにセキュリティで保護された属性を持たせたい場合は、この変数を `true` に設定します。

```js
s.writeSecureCookies = true;
```
