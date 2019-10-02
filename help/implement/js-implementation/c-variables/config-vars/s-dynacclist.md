---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# s.dynamicAccountList

> [!NOTE] この変 `s.dynamicAccountList` 数は、現在のAppMeasurementライブラリではサ [ポートされていません](../../c-appmeasurement-js/appmeasure-mjs.md)。 Hコードなど、従来のAppMeasurementでのみ使用されます。

この変 `s.dynamicAccountList` 数は、データの送信先のレポートスイートを動的に決定するのに役立ちます。 変数および変数と組み合わせて使 `dynamicAccountSelection` 用され `dynamicAccountMatch` ます。 のルールは、がに設 `dynamicAccountList` 定され `dynamicAccountSelection` ている場合 `true`に適用され、で指定したURLのセクションに適用されます `dynamicAccountMatch`。

## 構文と可能な値

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Valid input is a semicolon-separated list of name=value pairs (rules). 各リストには、次の項目が含まれます。

* One or more report suite ID's (separated by commas)
* An equals sign
* One or more URL filters (comma-separated)

文字列内では標準的な ASCII 文字のみを使用してください（空白は使用できません）。

## 例

次の例では、ページURLを、変数を `https://example.com/path2/?prod_id=12345`に、変 `dynamicAccountSelection` 数を `true`に設 `s_account` 定してい `examplersid`ます。

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## 注意事項、質問、ヒント

* この変数で示されるルールは、左から右の順で適用されます。If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. As a result, place more generic rules to the right of the list.
* If no rules match, the default report suite in `s_account` is used.
* If your page is saved to someone's hard drive or translated via a web-based translation engine (such as Google's translated pages), the dynamic account selection likely won't work.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.
* を使用して、 [!DNL Adobe Experience Cloud Debugger] 送信先のレポートスイートをテストします。
