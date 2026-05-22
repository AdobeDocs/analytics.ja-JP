---
title: cookieDomainPeriods
description: （非推奨） web サイトのトップレベルドメインにピリオドが含まれている場合に、AppMeasurementがCookieの保存場所を決定する際に役立ちます。
feature: Appmeasurement Implementation
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/bsJTIAuqcWoXWWus0oPME9LEwEMaiCGjd1ChmCuSjKY'
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 18%

---

# cookieDomainPeriods

>[!IMPORTANT]
>この変数は非推奨です。 次のいずれかを使用する場合：
>
>* AppMeasurement v2.26.x以降
>* Adobe Analytics拡張機能v1.9.4以降
>* Adobe Experience Cloud ID サービス
>
>該当するライブラリがCookieを設定するドメインを自動的に検出するため、この変数は何もしません。

`cookieDomainPeriods`変数は、トップレベルドメインに余分な期間があることを示すことで、AppMeasurementがAnalytics Cookieの設定場所を決定するのに役立ちました。 この変数により、AppMeasurementはトップレベルドメインの余分な期間に対応し、Cookieを正しい場所に設定できるようになりました。 web サイトのトップレベルドメインに追加期間が含まれていない場合、この変数は必要ありません。

* `example.co.uk` や `www.example.co.jp` などのドメインの場合、この変数を `"3"` に設定します。
* `example.nsw.gov.au`などのドメインの場合は、この変数を`"4"`に設定します。
* `example.com`や`products.example.org`などのドメインでは、この変数の設定を省略するか、`"2"`に設定します。

>[!TIP]
>
>この変数ではサブドメインは考慮しません。 例えば、サンプル URL `store.toys.example.com` では `cookieDomainPeriods` を設定しないでください。 AppMeasurementは、多くのサブドメインを持つURLでも`example.com`にCookieが保存されていることを認識します。

AppMeasurement v2.26.x以降の実装では、[`s_ac`](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/cookies/analytics) Cookieを使用して、適切なCookie ドメインを自動的に判断します。 ライブラリは、最初に2つのドメイン期間を含むCookieを書き込もうとします。 このCookieの設定が失敗した場合、そのCookieが成功するまでドメイン期間を含め、再試行されます。 このCookieは、一度設定すると直ちに削除されます。

## Web SDKを使用したCookie ドメイン期間

Web SDKは、Cookieを設定するための正しいドメインを自動的に決定します。

## Adobe Analytics拡張機能を使用したCookie ドメイン期間

**[!UICONTROL Domain Periods]**&#x200B;は、Adobe Analytics拡張機能を設定する際の[!UICONTROL Cookies] アコーディオンの下のフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL ドメインピリオド]」フィールドが表示されます。

ピリオドを含むトップレベルのドメインに対してのみ、このフィールドを`3`に設定します。 それ以外の場合、このフィールドは空白のままにできます。

## AppMeasurementおよびAnalytics拡張機能のカスタムコードエディターのCookie ドメイン期間

`cookieDomainPeriods`変数は、ピリオドを含むトップレベルドメインでのみ、通常`"3"`に設定される文字列です。 デフォルト値は`"2"`で、`.com`や`.org`などのほとんどのトップレベルドメインに対応します。

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
