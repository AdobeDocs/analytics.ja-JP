---
title: pageType
description: 現在のページが 404 エラーであるかどうかを調べます。
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 83%

---

# pageType

`pageType` 変数は、404 エラーなど、サイト上のエラーページを指定するために使用されるフラグです。この変数に `errorPage` 文字列が含まれている場合は、「Pages Not Found」ディメンションが設定されます。

>[!IMPORTANT]
>
> この変数は、エラーのないページに設定しないでください。

## Adobe Experience Platformでタグを使用したページタイプ

データ収集UIには、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および カスタムコードエディターの s.pageType

`s.pageType` 変数は文字列で、唯一の有効な値は `errorPage` です。この変数は、404 ページなど、サイトの任意のエラーページでこの値に設定します。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
> eVar を使用してエラーコードを収集し、訪問者がサイトで発生した特定のエラーに関する詳細を取得できます。
