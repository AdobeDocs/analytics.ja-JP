---
title: dynamicAccountList
description: 実装によるレポートスイートの決定方法に関するロジックを確立します。
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '258'
ht-degree: 100%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
> 動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。これらの変数は、現在の AppMeasurement ライブラリや Adobe Experience Platform Launch ではサポートされていません。

`s.dynamicAccountList` 変数は、`s_account` の値を動的に決定します。`dynamicAccountSelection` を `true` に設定すると、`dynamicAccountMatch` 変数が `dynamicAccountList` と比較されます 。一致が見つかった場合は、一致するレポートスイート ID が使用されます。

## 構文

この変数は、JavaScript ファイルによって自動的に解析される文字列です。

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

有効な入力は、rsid と値のペアをセミコロンで区切ったリストです。各リストには、次の項目が含まれます。

* 1 つ以上のレポートスイート ID（コンマ区切り）
* 等号
* 一致させる 1 つ以上の文字列（コンマ区切り）

文字列内では標準的な ASCII 文字のみを使用してください。スペースは含めないでください。

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
