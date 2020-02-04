---
title: cookieDomainPeriods
description: ドメインのサフィックスにピリオドが含まれている場合、AppMeasurementがcookieを保存するドメインを理解するのに役立ちます。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# cookieDomainPeriods

AppMeasurementは、ドメインとドメインサフィックスを調べてCookieの場所を判断します。 などのドメインの `example.com`場合、AppMeasurementはcookieを正しい場所に設定します。 ただし、その他のドメイン（など）で `example.co.uk`は、AppMeasurementが誤ってcookieをオンに設定している可能性がありま `co.uk`す。 ほとんどのブラウザーは、この無効なドメインに設定されたcookieを拒否し、訪問者の識別に問題が生じます。

この変 `cookieDomainPeriods` 数は、ドメインサフィックスに余分なピリオドが含まれていることを呼び出すことで、AppMeasurementがAnalytics cookieの設定場所を判断するのに役立ちます。 この変数を使用すると、AppMeasurementでドメインサフィックスに余分なピリオドを含め、適切な場所にcookieを設定できます。

* またはなどのドメ `example.com` インの `www.example.com`場合、この変数を設定する必要はありません。 必要に応じて、この変数をに設定できま `"2"`す。
* またはなどのドメイン `example.co.uk` の場合、 `www.example.co.jp`この変数をに設定しま `"3"`す。

> [!IMPORTANT] この変数にはサブドメインを考慮しないでください。 例えば、サンプルURLを設定 `cookieDomainPeriods` しないでください `store.toys.example.com`。 AppMeasurementは、多くのサブドメインを持つURL上でも、Cookieの保存先 `example.com`であることをデフォルトで認識します。

## Adobe Experience Platform Launchのドメインピリオド

「ドメインピリオド」は、Adobe Analytics拡張機能を設定す [!UICONTROL る際に] 、「cookies」アコーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「 [!UICONTROL Cookies] 」アコーディオンを展開すると、「 [!UICONTROL Domain Periods] 」フィールドが表示されます。

サフィックスにピリオドを含 `3` むドメインでのみ、このフィールドを設定します。 それ以外の場合は、このフィールドを空白のままにすることができます。

## AppMeasurementのs.cookieDomainPeriodsとカスタムコードエディターの起動

変数 `cookieDomainPeriods` は、通常、サフィックスにピリオドを含 `"3"`むドメインでのみに設定される文字列です。 デフォルト値はで、ほ `"2"`とんどのドメインに対応します。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
