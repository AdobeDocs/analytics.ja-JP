---
title: pageType
description: 現在のページが 404 エラーであるかどうかを調べます。
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# pageType

`pageType` 変数は、404 エラーなど、サイト上のエラーページを指定するために使用されるフラグです。この変数に `errorPage` 文字列が含まれている場合は、「Pages Not Found」ディメンションが設定されます。

>[!IMPORTANT] この変数は、エラーのないページに設定しないでください。

## Adobe Experience Platform Launch のページタイプ

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.pageType

`s.pageType` 変数は文字列で、唯一の有効な値は `errorPage` です。この変数は、404 ページなど、サイトの任意のエラーページでこの値に設定します。

```js
s.pageType = "errorPage";
```

>[!TIP] eVar を使用してエラーコードを収集し、訪問者がサイトで発生した特定のエラーに関する詳細を取得できます。
