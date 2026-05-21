---
title: fpcookieDomainPeriods
description: ドメインのサフィックスにピリオドが含まれていると、AppMeasurement が Cookie を保存するドメインをよりよく理解できます。
feature: Appmeasurement Implementation
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
TQID: https://experienceleague.adobe.com/c8ynLzlV-tctlh1Aw2TRBfgiLbwlP4cLB-UfrFFsgTU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 86%

---

# fpCookieDomainPeriods

`fpCookieDomainPeriods` 変数は、ドメインサフィックスに余分なピリオドが含まれていることを示して、AppMeasurement が Analytics Cookie の設定場所を判断するのに役立ちます。 この変数を使用すると、AppMeasurement はドメインサフィックスに余分なピリオドを含め、適切な場所に Cookie を設定できます。 この変数は [`cookieDomainPeriods`](cookiedomainperiods.md) の値を継承しますが、実装でファーストパーティ Cookie 使用する場合は、設定するのがベストプラクティスです。

* `example.com` や `www.example.com` などのドメインの場合、この変数を設定する必要はありませんが、 必要に応じて、`"2"` に設定できます。
* `example.co.uk` や `www.example.co.jp` などのドメインの場合、この変数を `"3"` に設定します。

>[!IMPORTANT]
>
>この変数ではサブドメインは考慮しません。 例えば、サンプル URL `store.toys.example.com` では `fpCookieDomainPeriods` を設定しないでください。 AppMeasurement は、多くのサブドメインを持つ URL 上でも、Cookie の保存先が `example.com` であることをデフォルトで認識します。

## Web SDKを使用した1st パーティドメイン期間

Web SDKでは、この変数を使用せずに適切なcookie ストレージドメインを判断できます。

## Adobe Analytics拡張機能を使用したファーストパーティドメイン期間

「ファーストパーティドメインピリオド」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL ファーストパーティドメインピリオド]」フィールドが表示されます。

サフィックスにピリオドを含むドメインでのみ、このフィールドを `3` に設定します。 それ以外の場合は、このフィールドを空白のままにすることができます。

## AppMeasurementおよびAnalytics拡張機能のカスタムコードエディターのs.fpCookieDomainPeriods

`fpCookieDomainPeriods` 変数は、通常、サフィックスにピリオドを含むドメインでのみで `"3"` に設定される文字列です。 デフォルト値は `"2"` で、ほとんどのドメインに対応します。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
