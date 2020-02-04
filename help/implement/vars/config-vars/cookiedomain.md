---
title: cookieDomain
description: cookieDomain変数は、cookieを設定するドメインを決定するのに役立ちます。
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# cookieDomain

> [!IMPORTANT] この変数は廃止されます。 代わりに、を `trackingServer` 使用します。

この変 `cookieDomain` 数は、AppMeasurementがcookieを設定するドメインを決定します。 この変数を使用すると、変数を使用する代わりにcookieドメインを明示的に設定で `cookieDomainPeriods` きます。

この変数は、次の両方の条件が満たさ **れた場合** にのみ使用する必要があります。

* 導入でファーストパーティcookieを使用する場合。 この変数は、を含む値を使用した実装では必 `trackingServer` 須ではありませ `sc.omtrdc.net`ん。
* ドメインのサフィックスにピリオドが含まれている場合。 例えば、この変数 `example.co.uk` を使用して、cookie `cookieDomain` ドメインが存在するかどうかを明示的に示すこ `example.co.uk` とができま `co.uk`す。

変数を使用する実装はごく少数で、そ `cookieDomain` の代わりに、のような代替変数を使 `cookieDomainPeriods` 用できます。

## Adobe Experience Platform LaunchのCookieドメイン

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.cookieDomainとカスタムコードエディターの起動

変 `cookieDomain` 数は文字列で、cookieを保存するドメインに設定されます。

```js
s.cookieDomain = "stats.example.com";
```
