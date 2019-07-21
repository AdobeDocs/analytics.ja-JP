---
description: 現在のページ URL または入力文字列に指定したクエリ文字列パラメーターが含まれる場合、その値を返します。
keywords: Analytics の導入
seo-description: 現在のページ URL または入力文字列に指定したクエリ文字列パラメーターが含まれる場合、その値を返します。
seo-title: Util.getQueryParam
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: 開発者と導入
uuid: 1fid148-3e52-46f2- a73f-003563f7a62c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Util.getQueryParam

現在のページ URL または入力文字列に指定したクエリ文字列パラメーターが含まれる場合、その値を返します。

重要なデータ（キャンペーントラッキングコード、内部検索キーワードなど）はページ上のクエリ文字列に含まれているので、getQueryParam はデータを取得して Analytics 変数に取り込むのに役立ちます。

このユーティリティは、[getQueryParam](../../implement/js-implementation/plugins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) プラグインに代わるものです。

**構文：**

```
s.Util.getQueryParam(key, [url], [delim])
```

>[!NOTE]
>
>ユーティリティの構文はプラグインの構文と異なります。

**パラメーター：**

| パラメーター | 説明 |
|---|---|
| key | （必須）取得するクエリ文字列パラメーターの名前。このパラメーターでは大文字と小文字が区別されます。 |
| url | (optional) Default url is `s.pageURL` or `window.location`. このパラメーターの値を指定すると、クエリパラメーターが取得される URL より優先されます。 |
| delim | （オプション）URL でのパラメーターの区切り文字デフォルトの区切り文字は「&amp;」です。ここで、「;」など代わりに使用するクエリ文字列の区切り文字を指定できます。 |

**戻り値：**

関数は、「キーが指定されていない場合、またはURLオプションが存在しない場合、またはURLにキーが見つからない場合、空の文字列を返します。URLにフラグメント区切り記号#が見つかった場合、フラグメント区切り文字の後にあるすべては考慮されません。キーが存在し、値に割り当てられている場合、値はデコードされて返され、返されます。

**例：**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

