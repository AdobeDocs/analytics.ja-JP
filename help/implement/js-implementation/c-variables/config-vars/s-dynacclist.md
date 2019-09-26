---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountList

[!DNL AppMeasurement]JavaScript 版 では、データ送信先のレポートスイートを動的に選択できます。 変数には、目的のレポートスイートを決定するために使用されるルールが含まれます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | "" |

この変数は、 と変 *`dynamicAccountSelection`* 数 *`dynamicAccountMatch`* を追加。 のルールは、 *`dynamicAccountList`* が「true」に設 *`dynamicAccountSelection`* 定され、で指定されたURLのセクションに適用される場合に適用されます *`dynamicAccountMatch`*。

のルールがページのURLに一致し *`dynamicAccountList`* ない場合は、で識別されたレポートスイートが使用 `s_account` されます。 この変数で示されるルールは、左から右の順で適用されます。ページ URL が複数のルールと一致する場合、最も左にあるルールを使用してレポートスイートが決定されます。そのため、より一般的なルールをリストの右側に移動する必要があります。

次の例では、ページURLは `www.mycompany.com/path1/?prod_id=12345` trueで `dynamicAccountSelection` 、 *は* true `s_account` に設定され、 `mysuitecom.`

| DynamicAccountList の値 | DynamicAccountMatch の値 | データを受信するレポートスイート |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1、mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom、mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

## 構文と可能な値

Folio Builder`dynamicAccountList` 変数は、name=value のペア（ルール）をセミコロンで区切ったリストです。リストの各要素には以下の項目が含まれる必要があります。

* 1 つ以上のレポートスイート ID（コンマ区切り）
* 等号
* 1 つ以上の URL フィルター（コンマ区切り）

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

文字列内では標準的な ASCII 文字のみを使用してください（空白は使用できません）。

## 例

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## 設定

なし

## 注意事項、質問、ヒント

* 動的なアカウント選択は、 [JavaScript 版 AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* ページ URL が複数のルールと一致する場合、最も左にあるルールが使用されます。
* 一致するルールがない場合、デフォルトのレポートスイートが使用されます。
* ページが他のユーザーのハードドライブに保存されているか、Web ベースの翻訳エンジンを介して翻訳されている場合（Google 翻訳後のページなど）は、動的アカウント選択はおそらく動作しません。より精度の高いトラッキングをおこなうには、`s_account` 変数をサーバーサイドで設定してください。
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* 動的アカウント選択を使用する場合は、新しいドメインを取得す *`dynamicAccountList`* るたびに必ず更新するようにしてください。
* 送信先のレポートスイートを識別する際には、[!DNL DigitalPulse Debugger] を使用します。The `dynamicAccountSelection` variable always overrides the value of `s_account`.
