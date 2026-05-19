---
title: dynamicAccountList
description: 実装によるレポートスイートの決定方法に関するロジックを確立します。
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
TQID: https://experienceleague.adobe.com/qqkQoYsBWdTDOIkNfregm4k11CoDEl3dOJ3HNCMIo3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 89%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
>動的アカウントは、レガシー JavaScript 実装（H コード）を使用した場合にのみサポートされます。 これらの変数は、現在のAppMeasurement ライブラリまたはAdobe Experience Platform Data Collectionではサポートされていません。

`s.dynamicAccountList` 変数は、`s_account` の値を動的に決定します。 `dynamicAccountSelection` を `true` に設定すると、`dynamicAccountMatch` 変数が `dynamicAccountList` と比較されます。 一致が見つかった場合は、一致するレポートスイート ID が使用されます。

## 構文

この変数は、JavaScript ファイルによって自動的に解析される文字列です。

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

有効な入力は、rsid と値のペアをセミコロンで区切ったリストです。 各リストには、次の項目が含まれます。

* 1 つ以上のレポートスイート ID（コンマ区切り）
* 等号
* 一致させる 1 つ以上の文字列（コンマ区切り）

文字列内では標準的な ASCII 文字のみを使用してください。 スペースは含めないでください。

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

* この変数で示されるルールは、左から右の順序で適用されます。 `dynamicAccountMatch` 変数が複数のルールと一致する場合、最も左にあるルールを使用してレポートスイートが決定されます。 そのため、より一般的なルールをリストの右側に移動する必要があります。
* 一致するルールがない場合、`s_account` のデフォルトレポートスイートが使用されます。
* ページが他のユーザーのハードドライブに保存されているか、Web ベースの翻訳エンジンを介して翻訳されている場合（Google 翻訳後のページなど）は、動的アカウント選択はおそらく動作しません。
* `dynamicAccountSelection` ルールは、`dynamicAccountMatch` で指定された URL のセクションにのみ適用されます。
* Adobe CX Enterprise Debuggerを使用して、宛先レポートスイートをテストします。
