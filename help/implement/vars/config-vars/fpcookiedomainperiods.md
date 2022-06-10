---
title: fpcookieDomainPeriods
description: ドメインのサフィックスにピリオドが含まれていると、AppMeasurement が Cookie を保存するドメインをよりよく理解できます。
feature: Variables
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 82%

---

# fpCookieDomainPeriods

`fpCookieDomainPeriods` 変数は、ドメインサフィックスに余分なピリオドが含まれていることを示して、AppMeasurement が Analytics Cookie の設定場所を判断するのに役立ちます。この変数を使用すると、AppMeasurement はドメインサフィックスに余分なピリオドを含め、適切な場所に Cookie を設定できます。この変数は [`cookieDomainPeriods`](cookiedomainperiods.md) の値を継承しますが、実装でファーストパーティ Cookie 使用する場合は、設定するのがベストプラクティスです。

* `example.com` や `www.example.com` などのドメインの場合、この変数を設定する必要はありませんが、必要に応じて、`"2"` に設定できます。
* `example.co.uk` や `www.example.co.jp` などのドメインの場合、この変数を `"3"` に設定します。

>[!IMPORTANT]
>
> この変数ではサブドメインは考慮しません。例えば、サンプル URL `store.toys.example.com` では `fpCookieDomainPeriods` を設定しないでください。AppMeasurement は、多くのサブドメインを持つ URL 上でも、Cookie の保存先が `example.com` であることをデフォルトで認識します。

## Web SDK を使用するファーストパーティドメインピリオド

Web SDK は、この変数を使用せずに、正しい Cookie ストレージドメインを判断できます。

## Adobe Analytics拡張機能を使用したファーストパーティドメインピリオド

「ファーストパーティドメインピリオド」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL ファーストパーティドメインピリオド]」フィールドが表示されます。

サフィックスにピリオドを含むドメインでのみ、このフィールドを `3` に設定します。それ以外の場合は、このフィールドを空白のままにすることができます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.fpCookieDomainPeriods

`fpCookieDomainPeriods` 変数は、通常、サフィックスにピリオドを含むドメインでのみで `"3"` に設定される文字列です。デフォルト値は `"2"` で、ほとんどのドメインに対応します。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
