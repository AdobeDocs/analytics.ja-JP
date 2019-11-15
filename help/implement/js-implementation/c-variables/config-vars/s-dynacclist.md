---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] この変 `s.dynamicAccountList` 数は、現在のAppMeasurementライブラリではサ [ポートされていません](../../c-appmeasurement-js/appmeasure-mjs.md)。 Hコードなど、従来のAppMeasurementでのみ使用されます。

この変 `s.dynamicAccountList` 数は、データの送信先のレポートスイートを動的に決定するのに役立ちます。 変数および変数と組み合わせて使 `dynamicAccountSelection` 用され `dynamicAccountMatch` ます。 The rules in `dynamicAccountList` are applied if `dynamicAccountSelection` is set to `true`, and they apply to the section of the URL specified in `dynamicAccountMatch`.

## 構文と可能な値

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

有効な入力は、name=valueのペア（ルール）をセミコロンで区切ったリストです。 各リストには、次の項目が含まれます。

* 1つ以上のレポートスイートID（コンマ区切り）
* 等号
* 1つ以上のURLフィルター（コンマ区切り）

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

* この変数で示されるルールは、左から右の順で適用されます。If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. その結果、より一般的なルールをリストの右側に配置します。
* If no rules match, the default report suite in `s_account` is used.
* ページが他のユーザーのハードドライブに保存されたり、Webベースの翻訳エンジン（Googleの翻訳済みページなど）を使用して翻訳された場合、動的アカウントの選択は動作しない可能性があります。
* `dynamicAccountSelection` ルールは、`dynamicAccountMatch` で指定された URL のセクションにのみ適用されます。
* Use the [!DNL Adobe Experience Cloud Debugger] to test the destination report suite.
