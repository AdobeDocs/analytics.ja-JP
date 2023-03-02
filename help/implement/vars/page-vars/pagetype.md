---
title: pageType
description: 現在のページが 404 エラーであるかどうかを調べます。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 8a6c639af7427a9975ccd061d059696d4611dff3
workflow-type: ht
source-wordcount: '208'
ht-degree: 100%

---

# pageType

`pageType` 変数は、404 エラーなど、サイト上のエラーページを指定するために使用されるフラグです。この変数に `errorPage` 文字列が含まれている場合は、「Pages Not Found」[ディメンション](/help/components/dimensions/pages-not-found.md)および[指標](/help/components/metrics/pages-not-found.md)が設定されます。

>[!IMPORTANT]
>
>この変数は、エラーのないページに設定しないでください。

## Web SDK を使用したページタイプ

ページタイプは、XDM フィールド `web.webPageDetails.isErrorPage` で [Adobe Analytics 用にマッピング](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja)されます。この XDM フィールドはブール値です。エラーページとしてフラグを立てるには `true` に設定し、エラーページでない場合は `false` に設定します。Adobe は、Analytics レポートスイートに送信される際に、ブール値を文字列値 `errorPage` に自動的に変換します。

## Adobe Analytics 拡張機能を使用したページタイプ

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement の s.pageType と Analytics 拡張機能のカスタムコードエディター

`s.pageType` 変数は文字列で、唯一の有効な値は `errorPage` です。この変数は、404 ページなど、サイトの任意のエラーページでこの値に設定します。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>eVar を使用してエラーコードを収集し、訪問者がサイトで発生した特定のエラーに関する詳細を取得できます。
