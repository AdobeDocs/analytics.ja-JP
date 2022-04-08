---
title: cookieDomainPeriods
description: ドメインのサフィックスにピリオドが含まれていると、AppMeasurement が Cookie を保存するドメインをよりよく理解できます。
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '291'
ht-degree: 100%

---

# cookieDomainPeriods

AppMeasurement は、ドメインとドメインサフィックスを調べて Cookie の場所を判断します。`example.com` などのドメインの場合、AppMeasurement は Cookie を正しい場所に設定します。ただし、`example.co.uk` などのその他のドメインでは、AppMeasurement が誤って Cookie を `co.uk` に設定している可能性があります。ほとんどのブラウザーは、この無効なドメインに設定された Cookie を拒否し、訪問者の識別に問題が生じます。

`cookieDomainPeriods` 変数は、ドメインサフィックスに余分なピリオドが含まれていることを示して、AppMeasurement が Analytics Cookie の設定場所を判断するのに役立ちます。この変数を使用すると、AppMeasurement はドメインサフィックスに余分なピリオドを含め、適切な場所に Cookie を設定できます。

* `example.com` や `www.example.com` などのドメインの場合、この変数を設定する必要はありませんが、必要に応じて、`"2"` に設定できます。
* `example.co.uk` や `www.example.co.jp` などのドメインの場合、この変数を `"3"` に設定します。

>[!IMPORTANT]
>
> この変数ではサブドメインは考慮しません。例えば、サンプル URL `store.toys.example.com` では `cookieDomainPeriods` を設定しないでください。AppMeasurement は、多くのサブドメインを持つ URL 上でも、Cookie の保存先が `example.com` であることをデフォルトで認識します。

## Adobe Experience Platform のタグを使用したドメインピリオド

「ドメインピリオド」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
1. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL ドメインピリオド]」フィールドが表示されます。

サフィックスにピリオドを含むドメインでのみ、このフィールドを `3` に設定します。それ以外の場合は、このフィールドを空白のままにすることができます。

## AppMeasurement および カスタムコードエディターの s.cookieDomainPeriods

`cookieDomainPeriods` 変数は、通常、サフィックスにピリオドを含むドメインでのみで `"3"` に設定される文字列です。デフォルト値は `"2"` で、ほとんどのドメインに対応します。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
