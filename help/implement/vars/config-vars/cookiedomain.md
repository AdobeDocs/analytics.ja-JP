---
title: cookieDomain
description: cookieDomain 変数は、Cookie を設定するドメインを決定するのに役立ちます。
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 87%

---

# cookieDomain

>[!IMPORTANT]
>
> この変数は廃止されています。代わりに、[`trackingServer`](trackingserver.md) を使用してください。

`cookieDomain` 変数は、AppMeasurement が Cookie を設定するドメインを決定します。[`cookieDomainPeriods`](cookiedomainperiods.md) 変数を使用すると、変数を使用する代わりに Cookie ドメインを明示的に設定できます。

この変数は、次の&#x200B;**両方**&#x200B;の条件が満たされた場合にのみ使用する必要があります。

* 実装でファーストパーティ Cookie を使用する場合。この変数は、`sc.adobedc.net` を含む [`trackingServer`](trackingserver.md) 値を使用した実装では必須ではありません。
* ドメインのサフィックスにピリオドが含まれている場合。例えば、`example.co.uk` は、`cookieDomain` 変数を使用して、Cookie ドメインが `example.co.uk` であって `co.uk` でないことを明示的に示すことができます。

`cookieDomain` 変数を使用する実装はごく少数で、その代わりに、[`cookieDomainPeriods`](cookiedomainperiods.md) のような代替変数を使用できます。

## Adobe Experience Platformでタグを使用するCookieドメイン

データ収集UIには、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.cookieDomain

`cookieDomain` 変数は文字列で、Cookie を保存するドメインに設定されます。

```js
s.cookieDomain = "stats.example.com";
```
