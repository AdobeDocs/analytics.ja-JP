---
title: dynamicAccountList
description: 導入によるレポートスイートの決定方法に関するロジックを確立します。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# s.dynamicAccountList

> [!IMPORTANT] 動的アカウントは、レガシーJavaScript実装（Hコード）を使用した場合にのみサポートされます。 これらの変数は、現在のAppMeasurementライブラリまたはAdobe Experience Platform Launchではサポートされていません。

変数 `s.dynamicAccountList` は、の値を動的に決定します `s_account`。 をに設 `dynamicAccountSelection` 定すると、変 `true`数が `dynamicAccountMatch` と比較されます `dynamicAccountList`。 一致が見つかった場合は、一致するレポートスイートIDが使用されます。

## 構文

この変数は、JavaScriptファイルによって自動的に解析される文字列です。

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

有効な入力は、rsidと値のペアをセミコロンで区切ったリストです。 各リストには、次の項目が含まれます。

* 1 つ以上のレポートスイート ID（コンマ区切り）
* 等号
* 一致させる1つ以上の文字列（コンマ区切り）

文字列には、標準のASCII文字のみを使用する必要があります。 スペースは含めないでください。

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
