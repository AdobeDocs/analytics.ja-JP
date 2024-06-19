---
title: cookieDomainPeriods
description: （非推奨） Web サイトのトップレベルドメインにピリオドが含まれている場合に、AppMeasurementが Cookie を保存する場所を決定するのに役立ちます。
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: c7e525b68898a6663f3b40e2293f959d4bd129b2
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

この `cookieDomainPeriods` 変数は、トップレベルドメインに余分な時間が含まれていることを示すことで、AppMeasurementが Analytics Cookie を設定する場所を決定するのに役立ちました。 この変数を使用すると、AppMeasurementはトップレベルドメインに余分な時間を格納し、Cookie を正しい場所に設定できました。 Web サイトのトップレベルドメインに追加の期間が含まれていない場合、この変数は不要です。

* `example.co.uk` や `www.example.co.jp` などのドメインの場合、この変数を `"3"` に設定します。
* のようなドメインの場合 `example.nsw.gov.au`、この変数をに設定します `"4"`.
* のようなドメインの場合 `example.com` または `products.example.org`、この変数の設定を省略するか、に設定します。 `"2"`.

>[!TIP]
>
> この変数ではサブドメインは考慮しません。例えば、サンプル URL `store.toys.example.com` では `cookieDomainPeriods` を設定しないでください。AppMeasurementは、Cookie が次の場所に保存されていることを認識します `example.com`（多くのサブドメインを持つ URL の場合も同様）。

AppMeasurement v2.26.x 以降での実装の場合、 [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie は、正しい cookie ドメインを自動的に判断するために使用されます。 ライブラリは最初に、2 つのドメインピリオドを含む cookie を書き込もうとします。 この cookie の設定に失敗した場合は、成功するまでドメインピリオドを含めて再試行します。 この cookie は設定後すぐに削除されます。

## Web SDK を使用した cookie ドメインピリオド

Web SDK は、Cookie を設定する適切なドメインを自動的に決定します。

## Adobe Analytics拡張機能を使用した cookie ドメインピリオド

**[!UICONTROL ドメイン期間]** は、の下のフィールドです [!UICONTROL の Cookie] Adobe Analytics拡張機能の設定時のアコーディオン。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL ドメインピリオド]」フィールドが表示されます。

このフィールドを次のように設定 `3` ピリオドを含む最上位ドメインのみで使用します。 それ以外の場合は、このフィールドを空白にできます。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの cookie ドメインピリオド

この `cookieDomainPeriods` 変数は、通常、に設定される文字列です `"3"`（ピリオドを含む最上位ドメインのみ）。 デフォルト値はです `"2"`。以下のような最上位ドメインのほとんどに対応しています `.com` および `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
