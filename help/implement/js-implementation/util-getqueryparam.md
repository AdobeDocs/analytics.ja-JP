---
description: 現在のページ URL または入力文字列に指定したクエリ文字列パラメーターが含まれる場合、その値を返します。
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: Developer and implementation
uuid: 1fecd148-3e52-46f2-a73f-003563f7a62c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.getQueryParam

現在のページ URL または入力文字列に指定したクエリ文字列パラメーターが含まれる場合、その値を返します。

重要なデータ（キャンペーントラッキングコード、内部検索キーワードなど）はページ上のクエリ文字列に含まれているので、getQueryParam はデータを取得して Analytics 変数に取り込むのに役立ちます。

このユーティリティは、[getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md) プラグインに代わるものです。

**構文：**

```
s.Util.getQueryParam(key, [url], [delim])
```

> [!NOTE]ユーティリティの構文はプラグインの構文と異なります。

**パラメーター:**

| パラメーター | 説明 |
|---|---|
| key | （必須）取得するクエリ文字列パラメーターの名前。このパラメーターでは大文字と小文字が区別されます。 |
| url | （オプション）デフォルトの url は、`s.pageURL` または `window.location` です。このパラメーターの値を指定すると、クエリパラメーターが取得される URL より優先されます。 |
| delim | （オプション）URL でのパラメーターの区切り文字デフォルトの区切り文字は「&amp;」です。ここで、「;」など代わりに使用するクエリ文字列の区切り文字を指定できます。 |

**戻り値:**

キーが指定されていない場合、URL オプションが存在しない場合、または URL にキーが見つからない場合は、空の文字列 "" が返されます。URL 内にフラグメント区切り記号 # が見つかった場合、フラグメント区切り記号の後のすべての要素は考慮されなくなります。キーが存在し、値に割り当てられている場合、値は URL デコードされて返されます。

**例：**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

