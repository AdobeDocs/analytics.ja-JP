---
title: cookieDomainPeriods
description: ドメインのサフィックスにピリオドが含まれている場合、AppMeasurementがCookieを保存するドメインを理解するのに役立ちます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# fpCookieDomainPeriods

この変 `fpCookieDomainPeriods` 数は、ドメインサフィックスに余分なピリオドが含まれていることを呼び出すことで、AppMeasurementがAnalytics cookieの設定場所を判断するのに役立ちます。 この変数を使用すると、AppMeasurementでドメインサフィックスに余分なピリオドを含め、適切な場所にcookieを設定できます。 これはの値を継承しますが、ファ [`cookieDomainPeriods`](cookiedomainperiods.md)ーストパーティcookieの実装を使用する場合は、これを設定することがベストプラクティスとなります。

* またなどのドメ `example.com` インの `www.example.com`場合、この変数を設定する必要はありません。 必要に応じて、この変数をに設定できま `"2"`す。
* またはなどのドメイン `example.co.uk` の場合、 `www.example.co.jp`この変数をに設定しま `"3"`す。

> [!IMPORTANT] この変数に対してはサブドメインを考慮しないでください。 例えば、サンプルURLを設定 `fpCookieDomainPeriods` しないでください `store.toys.example.com`。 AppMeasurementは、多くのサブドメインを持つURL上でも、Cookieの保存先 `example.com`であることをデフォルトで認識します。

## Adobe Experience Platform Launchのファーストパーティドメインピリオド数

ファーストパーティドメインピリオドは、Adobe Analyticsの拡張機能を設定す [!UICONTROL Cookies] る際に、アコーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオ [!UICONTROL Cookies] ンを展開すると、フィールドが表示 [!UICONTROL First-party Domain Periods] されます。

サフィックスにピリオドを含 `3` むドメインでのみ、このフィールドをに設定します。 それ以外の場合は、このフィールドを空白のままにすることができます。

## AppMeasurementのs.fpCookieDomainPeriodsとカスタムコードエディターの起動

変数 `fpCookieDomainPeriods` は、通常、サフィックスにピリオドを含 `"3"`むドメインのみに設定される文字列です。 デフォルト値はで、ほ `"2"`とんどのドメインに対応しています。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
