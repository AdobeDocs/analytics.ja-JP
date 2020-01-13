---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] `s.dynamicAccountList` 変 数は、[現在の AppMeasurement ライブラリ](../../c-appmeasurement-js/appmeasure-mjs.md)ではサポートされていません。H コードなど、従来の AppMeasurement でのみ使用されます。

`s.dynamicAccountList` 変数は、データの送信先のレポートスイートを動的に決定するのに役立ちます。`dynamicAccountSelection` 変数および `dynamicAccountMatch` 変数と組み合わせて使用されます。`dynamicAccountList` のルールは `dynamicAccountSelection` が「`true`」に設定されている場合に適用され、`dynamicAccountMatch` で指定されている URL のセクションに適用されます。

## 構文と可能な値

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

有効な入力は、name=value のペア（ルール）をセミコロンで区切ったリストです。各リストには、次の項目が含まれます。

* 1 つ以上のレポートスイート ID（コンマ区切り）
* 等号
* 1 つ以上の URL フィルター（コンマ区切り）

文字列内では標準的な ASCII 文字のみを使用してください（空白は使用できません）。

## 例

次の例では、ページ URL は`https://example.com/path2/?prod_id=12345`で、`dynamicAccountSelection` 変数は `true` に設定され、`s_account` 変数は `examplersid` に設定されています。

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

* この変数で示されるルールは、左から右の順で適用されます。`dynamicAccountMatch` 変数が複数のルールと一致する場合、最も左にあるルールを使用してレポートスイートが決定されます。そのため、より一般的なルールをリストの右側に移動する必要があります。
* 一致するルールがない場合、`s_account` のデフォルトレポートスイートが使用されます。
* ページが他のユーザーのハードドライブに保存されているか、Web ベースの翻訳エンジンを介して翻訳されている場合（Google 翻訳後のページなど）は、動的アカウント選択はおそらく動作しません。
* `dynamicAccountSelection` ルールは、`dynamicAccountMatch` で指定された URL のセクションにのみ適用されます。
* 送信先レポートスイートをテストする場合は、[!DNL Adobe Experience Cloud Debugger] を使用してください。
