---
title: cookieDomainPeriods
description: ドメインのサフィックスにピリオドが含まれていると、AppMeasurement が Cookie を保存するドメインをよりよく理解できます。
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: fe33da47c109adacb8162c7165ad4c63bd65c08d
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 43%

---


# cookieDomainPeriods

AppMeasurement は、ドメインとドメインサフィックスを調べて Cookie の場所を判断します。`example.com` などのドメインの場合、AppMeasurement は Cookie を正しい場所に設定します。ただし、`example.co.uk` などのその他のドメインでは、AppMeasurement が誤って Cookie を `co.uk` に設定している可能性があります。ほとんどのブラウザーは、この無効なドメインに設定された Cookie を拒否し、訪問者の識別に問題が生じます。

`cookieDomainPeriods` 変数は、ドメインサフィックスに余分なピリオドが含まれていることを示して、AppMeasurement が Analytics Cookie の設定場所を判断するのに役立ちます。この変数を使用すると、AppMeasurement はドメインサフィックスに余分なピリオドを含め、適切な場所に Cookie を設定できます。

* `example.com` や `www.example.com` などのドメインの場合、この変数を設定する必要はありませんが、必要に応じて、`"2"` に設定できます。
* `example.co.uk` や `www.example.co.jp` などのドメインの場合、この変数を `"3"` に設定します。


>[!IMPORTANT]
>
> この変数ではサブドメインは考慮しません。例えば、サンプル URL `store.toys.example.com` では `cookieDomainPeriods` を設定しないでください。AppMeasurement は、多くのサブドメインを持つ URL 上でも、Cookie の保存先が `example.com` であることをデフォルトで認識します。


## Cookie ドメインピリオド、サードパーティ Cookie および従来の訪問者 ID

( 推奨されるExperience CloudID サービスではなく ) 従来のAdobe Analytics訪問者 ID を使用している場合にのみ、 `cookieDomainPeriods` は、サードパーティ Cookie がブロックされているかどうかに応じて、訪問者の識別方法に影響を与える場合があります。

次の表に、考えられる 4 つのシナリオを示します。

| シナリオ | `cookieDomainPeriods` 設定は次のとおりです… | サードパーティ Cookie がブロックされている場合 | 従来のAdobe Analytics訪問者 ID サービスを使用した場合の結果 |
|:---:|---|---|---|
| 1 | <span style="color:green">正しい</span> | × | 訪問者は、 `s_vi` cookie を使用し、サーバー側を設定します。 |
| 2 | <span style="color:green">正しい</span> | ○ | 訪問者はフォールバックで識別されます `s_fid` cookie、クライアントサイド（ファーストパーティのページドメイン）を設定します。 |
| 3 | <span style="color:red">誤った</span> | × | 訪問者は、ユーザーエージェントと IP アドレスの組み合わせに基づくフォールバック識別子で識別されます。 <br/>AppMeasurementは、cookie をサードパーティ cookie として設定するよう強制されます。<br/> The `s_vi` 次の場合に cookie が設定される可能性があります： `cookieDomainPeriods` が適切に送信されない。 |
| 4 | <span style="color:red">誤った</span> | ○ | 訪問者は、ユーザーエージェントと IP アドレスの組み合わせに基づくフォールバック識別子で識別されます。<br/>AppMeasurementは、cookie をブロックされたサードパーティ cookie として強制的に設定するので、cookie は設定されません。 |

>[!CAUTION]
>
>誤ってを設定した可能性があります `cookieDomainPeriods` <span style="color:red">誤った</span> ( デフォルト値の `"2"`) を使用する場合は、 `example.co.uk`. この暗黙の誤った設定結果は、シナリオ 3 または 4 に従って訪問者を識別することになります。
>
>AppMeasurementリリース 2.26.x 以降のでの設定 `cookieDomainPeriods` は適切な値で自動的に適用されるので、シナリオ 1 または 2 のみが可能です。 AppMeasurementリリース 2.26.x 以降に更新した場合、現在、訪問者を誤って識別しています（シナリオ 3 または 4）が、更新に大きな影響があります。
>
>* 訪問者識別子はリセット中で、訪問者は新規訪問者として表示されます。 新しいアクティビティを以前の訪問者識別子に関連付ける方法はありません。
>* Cookie が設定されている ( 例えば、リンクトラッキングや Activity Map の場合、`s_sq` cookie) を使用している場合は除外され、レポートに突然の違いが生じます。
>
>正しく設定中 `cookieDomainPeriods` AppMeasurementと Analytics の機能を改善するには、AppMeasurementライブラリのアップグレードによる変更の影響を受けているかどうかを評価することをお勧めします。
>
> 詳しくは、 [Analytics の cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=ja) を参照してください。

## Web SDK を使用した Cookie ドメインピリオド

Web SDK は、この変数を使用せずに、正しい Cookie ストレージドメインを判断できます。

## Adobe Analytics拡張機能を使用する Cookie ドメインピリオド

「ドメインピリオド」は、Adobe Analytics 拡張機能を設定する際に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL ドメインピリオド]」フィールドが表示されます。

サフィックスにピリオドを含むドメインでのみ、このフィールドを `3` に設定します。それ以外の場合は、このフィールドを空白のままにすることができます。

## コードAppMeasurementと Analytics 拡張機能のカスタムコードエディターでの Cookie ドメインピリオド

次の設定が可能です。 `cookieDomainPeriods` 変数を使用します。

`cookieDomainPeriods` 変数は、通常、サフィックスにピリオドを含むドメインでのみで `"3"` に設定される文字列です。デフォルト値は `"2"` で、ほとんどのドメインに対応します。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
