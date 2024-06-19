---
title: cookieDomain
description: （廃止） Cookie を設定するドメインを決定するのに役立ちます。
feature: Variables
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 77%

---

# cookieDomain

>[!IMPORTANT]
> この変数は廃止されています。代わりに、[`trackingServer`](trackingserver.md) を使用してください。

`cookieDomain` 変数は、AppMeasurement が Cookie を設定するドメインを決定します。[`cookieDomainPeriods`](cookiedomainperiods.md) 変数を使用すると、変数を使用する代わりに Cookie ドメインを明示的に設定できます。

この変数は、次の&#x200B;**両方**&#x200B;の条件が満たされた場合にのみ使用する必要があります。

* 実装でファーストパーティ Cookie を使用する場合。この変数は、`sc.adobedc.net` を含む [`trackingServer`](trackingserver.md) 値を使用した実装では必須ではありません。
* ドメインのサフィックスにピリオドが含まれている場合。例えば、`example.co.uk` は、`cookieDomain` 変数を使用して、Cookie ドメインが `example.co.uk` であって `co.uk` でないことを明示的に示すことができます。

`cookieDomain` 変数を使用する実装はごく少数で、その代わりに、[`cookieDomainPeriods`](cookiedomainperiods.md) のような代替変数を使用できます。

## Web SDK を使用した Cookie ドメイン

Web SDK は、この変数を使用せずに正しい cookie ストレージドメインを決定できます。

## Adobe Analytics拡張機能を使用した cookie ドメイン

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの s.cookieDomain と Analytics 拡張機能のカスタムコードエディター

`cookieDomain` 変数は文字列で、Cookie を保存するドメインに設定されます。

```js
s.cookieDomain = "stats.example.com";
```
