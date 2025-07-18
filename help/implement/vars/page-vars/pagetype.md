---
title: pageType
description: 現在のページが 404 エラーであるかどうかを調べます。
feature: Appmeasurement Implementation
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 75%

---

# pageType

`pageType` 変数は、404 エラーなど、サイト上のエラーページを指定するために使用されるフラグです。この変数に `errorPage` 文字列が含まれている場合は、「Pages Not Found」[ディメンション](/help/components/dimensions/pages-not-found.md)および[指標](/help/components/metrics/pages-not-found.md)が設定されます。

>[!IMPORTANT]
>
>この変数は、エラーのないページに設定しないでください。

## Web SDK を使用したページタイプ

チャネルは、次の変数にマッピングされます。

* [XDM オブジェクト ](/help/implement/aep-edge/xdm-var-mapping.md):`xdm.web.webPageDetails.isErrorPage` – この XDM フィールドはブール値です。エラーページとしてフラグを立てるには `true` に設定し、エラーページでない場合は `false` に設定します。
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageType` – このデータオブジェクトフィールドは文字列です。そのようにフラグを立てるには、`"errorPage"` に設定します。

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
