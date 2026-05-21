---
title: pageType
description: 現在のページが 404 エラーであるかどうかを調べます。
feature: Appmeasurement Implementation
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
TQID: https://experienceleague.adobe.com/SD-hwWJmZby-y99FIZHrnevSBsVqD6T5gwovn5tJfxo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 75%

---

# pageType

`pageType` 変数は、404 エラーなど、サイト上のエラーページを指定するために使用されるフラグです。 この変数に `errorPage` 文字列が含まれている場合は、「Pages Not Found」[ディメンション](/help/components/dimensions/pages-not-found.md)および[指標](/help/components/metrics/pages-not-found.md)が設定されます。

>[!IMPORTANT]
>
>この変数は、エラーのないページに設定しないでください。

## Web SDK を使用したページタイプ

チャネルは次の変数にマッピングされます。

* [XDM オブジェクト ](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.isErrorPage` – このXDM フィールドはブール値です。エラーページとしてフラグを立てるには`true`に設定し、エラーページでない場合は`false`に設定します。
* [ データオブジェクト ](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageType` – このデータオブジェクトフィールドは文字列です。フラグを設定するには、`"errorPage"`に設定します。

## Adobe Analytics 拡張機能を使用したページタイプ

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement の s.pageType と Analytics 拡張機能のカスタムコードエディター

`s.pageType` 変数は文字列で、唯一の有効な値は `errorPage` です。 この変数は、404 ページなど、サイトの任意のエラーページでこの値に設定します。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>eVar を使用してエラーコードを収集し、訪問者がサイトで発生した特定のエラーに関する詳細を取得できます。
