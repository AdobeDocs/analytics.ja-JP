---
title: cookieDomain
description: cookieDomain 変数は、Cookie を設定するドメインを決定するのに役立ちます。
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 100%

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

## Adobe Experience Platform Launch の Cookie ドメイン

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.cookieDomain

`cookieDomain` 変数は文字列で、Cookie を保存するドメインに設定されます。

```js
s.cookieDomain = "stats.example.com";
```
