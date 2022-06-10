---
title: pageType
description: 現在のページが 404 エラーであるかどうかを調べます。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 77%

---

# pageType

`pageType` 変数は、404 エラーなど、サイト上のエラーページを指定するために使用されるフラグです。この変数に `errorPage` 文字列が含まれている場合は、「Pages Not Found」ディメンションが設定されます。

>[!IMPORTANT]
>
> この変数は、エラーのないページに設定しないでください。

## Adobe Analytics拡張機能を使用したページタイプ

Adobe Analytics拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.pageType

`s.pageType` 変数は文字列で、唯一の有効な値は `errorPage` です。この変数は、404 ページなど、サイトの任意のエラーページでこの値に設定します。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
> eVar を使用してエラーコードを収集し、訪問者がサイトで発生した特定のエラーに関する詳細を取得できます。
