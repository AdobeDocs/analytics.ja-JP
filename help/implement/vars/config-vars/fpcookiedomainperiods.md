---
title: cookieDomainPeriods
description: ドメインのサフィックスにピリオドが含まれていると、AppMeasurement が Cookie を保存するドメインをよりよく理解できます。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# fpCookieDomainPeriods

`fpCookieDomainPeriods` 変数は、ドメインサフィックスに余分なピリオドが含まれていることを示して、AppMeasurement が Analytics Cookie の設定場所を判断するのに役立ちます。この変数を使用すると、AppMeasurement はドメインサフィックスに余分なピリオドを含め、適切な場所に Cookie を設定できます。この変数は [`cookieDomainPeriods`](cookiedomainperiods.md) の値を継承しますが、実装でファーストパーティ Cookie 使用する場合は、設定するのがベストプラクティスです。

* `example.com` や `www.example.com` などのドメインの場合、この変数を設定する必要はありませんが、必要に応じて、`"2"` に設定できます。
* `example.co.uk` や `www.example.co.jp` などのドメインの場合、この変数を `"3"` に設定します。

>[!IMPORTANT] この変数ではサブドメインは考慮しません。例えば、サンプル URL `store.toys.example.com` では `fpCookieDomainPeriods` を設定しないでください。AppMeasurement は、多くのサブドメインを持つ URL 上でも、Cookie の保存先が `example.com` であることをデフォルトで認識します。

## Adobe Experience Platform Launch の「ファーストパーティドメインピリオド」

「ファーストパーティドメインピリオド」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオ [!UICONTROL Cookies] ンを展開すると、フィールドが表示 [!UICONTROL First-party Domain Periods] されます。

サフィックスにピリオドを含むドメインでのみ、このフィールドを `3` に設定します。それ以外の場合は、このフィールドを空白のままにすることができます。

## AppMeasurement および Launch カスタムコードエディターの s.fpCookieDomainPeriods 

`fpCookieDomainPeriods` 変数は、通常、サフィックスにピリオドを含むドメインでのみで `"3"` に設定される文字列です。デフォルト値は `"2"` で、ほとんどのドメインに対応します。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
