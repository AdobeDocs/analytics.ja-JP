---
title: cookieDomainPeriods
description: （非推奨） Web サイトのトップレベルドメインにピリオドが含まれている場合に、AppMeasurementが Cookie を保存する場所を決定するのに役立ちます。
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 1cdcc748e50c7eeffa98897006154aa0953ce7e3
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 18%

---

# cookieDomainPeriods

>[!IMPORTANT]
>この変数は非推奨（廃止予定）です。 次のいずれかを使用する場合：
>
>* AppMeasurement v2.26.x 以降
>* Adobe Analytics extension v1.9.4 以降
>* Adobe Experience Cloud ID サービス
>
>該当するライブラリが Cookie を設定するドメインを自動的に検出するので、この変数は何もしません。

`cookieDomainPeriods` 変数は、トップレベルドメインに余分な期間が含まれていることを示すことで、AppMeasurementが Analytics Cookie を設定する場所を決定するのに役立ちました。 この変数を使用すると、AppMeasurementはトップレベルドメインに余分な時間を格納し、Cookie を正しい場所に設定できました。 Web サイトのトップレベルドメインに追加の期間が含まれていない場合、この変数は不要です。

* `example.co.uk` や `www.example.co.jp` などのドメインの場合、この変数を `"3"` に設定します。
* `example.nsw.gov.au` などのドメインの場合、この変数を `"4"` に設定します。
* `example.com` や `products.example.org` などのドメインの場合、この変数の設定を省略するか、`"2"` に設定します。

>[!TIP]
>
> この変数ではサブドメインは考慮しません。例えば、サンプル URL `store.toys.example.com` では `cookieDomainPeriods` を設定しないでください。AppMeasurementは、多くのサブドメインを持つ URL であっても、Cookie が `example.com` に保存されることを認識します。

AppMeasurement v2.26.x 以降での実装の場合、正しい cookie ドメインを自動的に判断するには、[`s_ac`](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/cookies/analytics) cookie が使用されます。 ライブラリは最初に、2 つのドメインピリオドを含む cookie を書き込もうとします。 この cookie の設定に失敗した場合は、成功するまでドメインピリオドを含めて再試行します。 この cookie は設定後すぐに削除されます。

## Web SDK を使用した cookie ドメインピリオド

Web SDK は、Cookie を設定する適切なドメインを自動的に決定します。

## Adobe Analytics拡張機能を使用した cookie ドメインピリオド

「**[!UICONTROL ドメインピリオド]**」は、Adobe Analytics拡張機能を設定する際に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL ドメインピリオド]」フィールドが表示されます。

このフィールドを、ピリオドを含む最上位ドメインにのみ `3` 用するように設定します。 それ以外の場合は、このフィールドを空白にできます。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの cookie ドメインピリオド

`cookieDomainPeriods` 変数は、通常、ピリオドを含む最上位ドメインでのみ `"3"` に設定される文字列です。 デフォルト値は `"2"` で、`.com` や `.org` などの最上位ドメインのほとんどに対応しています。

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
