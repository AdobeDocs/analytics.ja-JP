---
title: pageType
description: 現在のページが 404 エラーであるかどうかを調べます。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 8a6c639af7427a9975ccd061d059696d4611dff3
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 56%

---

# pageType

`pageType` 変数は、404 エラーなど、サイト上のエラーページを指定するために使用されるフラグです。この変数に文字列が含まれる場合 `errorPage`を入力すると、「エラーページ (404)」が入力されます [ディメンション](/help/components/dimensions/pages-not-found.md) および [指標](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
> この変数は、エラーのないページに設定しないでください。

## Web SDK を使用したページタイプ

ページタイプ： [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) XDM フィールドの下 `web.webPageDetails.isErrorPage`. この XDM フィールドはブール値です。設定する `true` エラーページとしてフラグを設定するか、 `false` エラーページでない場合は。 Adobeは、ブール値を文字列値に自動的に変換します `errorPage` Analytics レポートスイートに送信されるタイミング。

## Adobe Analytics拡張機能を使用したページタイプ

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.pageType

`s.pageType` 変数は文字列で、唯一の有効な値は `errorPage` です。この変数は、404 ページなど、サイトの任意のエラーページでこの値に設定します。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
> eVar を使用してエラーコードを収集し、訪問者がサイトで発生した特定のエラーに関する詳細を取得できます。
