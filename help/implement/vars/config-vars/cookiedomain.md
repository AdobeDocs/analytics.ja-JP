---
title: cookieDomain
description: cookieDomain変数は、cookieを設定するドメインを判断するのに役立ちます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# cookieDomain

> [!IMPORTANT] この変数は廃止されます。 代わりに、を [`trackingServer`](trackingserver.md) 使用します。

この変 `cookieDomain` 数は、AppMeasurementがcookieを設定するドメインを決定します。 この変数を使用すると、変数を使用する代わりに、cookieドメインを明示的に設定で [`cookieDomainPeriods`](cookiedomainperiods.md) きます。

この変数は、次の両方の条件が満たさ **れた場** 合にのみ使用する必要があります。

* 導入でファーストパーティcookieを使用する場合。 この変数は、を含む値を使用した実装では必 [`trackingServer`](trackingserver.md) 須ではありませ `sc.omtrdc.net`ん。
* ドメインのサフィックスにピリオドが含まれている場合。 例えば、この変数 `example.co.uk` を使用して、cookie `cookieDomain` ドメインがではなく、であることを明示的に示すこ `example.co.uk` とができま `co.uk`す。

変数を使用する実装はごく少数で、そ `cookieDomain` の場合でも、のような代替変数を代わ [`cookieDomainPeriods`](cookiedomainperiods.md) りに使用できます。

## Adobe Experience Platform LaunchのCookieドメイン

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.cookieDomainとカスタムコードエディターの起動

変数 `cookieDomain` は文字列で、cookieを保存するドメインに設定されます。

```js
s.cookieDomain = "stats.example.com";
```
