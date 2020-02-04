---
title: cookieDomainPeriods
description: ドメインのサフィックスにピリオドが含まれている場合、AppMeasurementがcookieを保存するドメインを理解するのに役立ちます。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# fpCookieDomainPeriods

この変 `fpCookieDomainPeriods` 数は、ドメインサフィックスに余分なピリオドが含まれていることを呼び出すことで、AppMeasurementがAnalytics cookieの設定場所を判断するのに役立ちます。 この変数を使用すると、AppMeasurementでドメインサフィックスに余分なピリオドを含め、適切な場所にcookieを設定できます。 これはの値を継承しますが、フ `cookieDomainPeriods`ァーストパーティcookieの実装を使用する場合は、これもベストプラクティスとして設定します。

* またはなどのドメ `example.com` インの `www.example.com`場合、この変数を設定する必要はありません。 必要に応じて、この変数をに設定できま `"2"`す。
* またはなどのドメイン `example.co.uk` の場合、 `www.example.co.jp`この変数をに設定しま `"3"`す。

> [!IMPORTANT] この変数にはサブドメインを考慮しないでください。 例えば、サンプルURLを設定 `fpCookieDomainPeriods` しないでください `store.toys.example.com`。 AppMeasurementは、多くのサブドメインを持つURL上でも、Cookieの保存先 `example.com`であることをデフォルトで認識します。

## Adobe Experience Platform Launchのファーストパーティドメインピリオド数

ファーストパーティドメインピリオドは、Adobe Analytics拡張機能を設定する際に [!UICONTROL 、「] Cookies」アコーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「 [!UICONTROL Cookies] 」アコーディオンを展開すると、「ファース [!UICONTROL トパーティドメイン期間] 」フィールドが表示されます。

サフィックスにピリオドを含 `3` むドメインでのみ、このフィールドを設定します。 それ以外の場合は、このフィールドを空白のままにすることができます。

## AppMeasurementのs.fpCookieDomainPeriodsとカスタムコードエディターの起動

変数 `fpCookieDomainPeriods` は、通常、サフィックスにピリオドを含 `"3"`むドメインでのみに設定される文字列です。 デフォルト値はで、ほ `"2"`とんどのドメインに対応します。

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
