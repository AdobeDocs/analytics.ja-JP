---
title: cookieDomain
description: （退職済み） Cookieを設定するドメインを決定するのに役立ちます。
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
TQID: https://experienceleague.adobe.com/z6occeGLpxezOj7go2DrwG-j-fc9yBuGyHSmZJK9RfQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 77%

---

# cookieDomain

>[!IMPORTANT]
>この変数は廃止されています。 代わりに、[`trackingServer`](trackingserver.md) を使用してください。

`cookieDomain` 変数は、AppMeasurement が Cookie を設定するドメインを決定します。 [`cookieDomainPeriods`](cookiedomainperiods.md) 変数を使用すると、変数を使用する代わりに Cookie ドメインを明示的に設定できます。

この変数は、次の&#x200B;**両方**&#x200B;の条件が満たされた場合にのみ使用する必要があります。

* 実装でファーストパーティ Cookie を使用する場合。 この変数は、`sc.adobedc.net` を含む [`trackingServer`](trackingserver.md) 値を使用した実装では必須ではありません。
* ドメインのサフィックスにピリオドが含まれている場合。 例えば、`example.co.uk` は、`cookieDomain` 変数を使用して、Cookie ドメインが `example.co.uk` であって `co.uk` でないことを明示的に示すことができます。

`cookieDomain` 変数を使用する実装はごく少数で、その代わりに、[`cookieDomainPeriods`](cookiedomainperiods.md) のような代替変数を使用できます。

## Web SDKを使用したCookie ドメイン

Web SDKでは、この変数を使用せずに適切なcookie ストレージドメインを判断できます。

## Adobe Analytics拡張機能を使用したCookie ドメイン

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.cookieDomainとAnalytics拡張機能のカスタムコードエディター

`cookieDomain` 変数は文字列で、Cookie を保存するドメインに設定されます。

```js
s.cookieDomain = "stats.example.com";
```
