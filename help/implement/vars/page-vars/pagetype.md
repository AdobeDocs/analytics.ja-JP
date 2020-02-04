---
title: pageType
description: 現在のページが404エラーであるかどうかを調べます。
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

この変 `pageType` 数は、404エラーなど、サイト上のエラーページを指定するために使用されるフラグです。 この変数に文字列が含まれてい `errorPage`る場合は、「Pages Not Found」ディメンションが設定されます。

> [!IMPORTANT] この変数は、エラーのないページに設定しないでください。

## Adobe Experience Platform Launchのページタイプ

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.pageTypeとカスタムコードエディターの起動

変 `s.pageType` 数は、値が有効な値の `errorPage` みである文字列です。 この変数は、404ページなど、サイトの任意のエラーページでこの値に設定します。

```js
s.pageType = "errorPage";
```

> [!TIP] eVarを使用してエラーコードを収集し、訪問者がサイトで発生した特定のエラーに関する詳細を取得できます。
