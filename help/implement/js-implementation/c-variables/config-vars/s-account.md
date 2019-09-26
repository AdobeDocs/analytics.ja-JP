---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.account

 変数は、データの保存とレポートをおこなうレポートスイートを決定します。

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. レポートスイート ID はアドビが決定します。

## パラメーター

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 40 バイト | In the URL path | 該当なし | 該当なし |

各レポートスイート ID は、[!DNL Admin Console] で作成された値と一致している必要があります。各レポートスイート ID は 40 バイト以下にする必要がありますが、すべてのレポートスイートの合計（コンマ区切りリスト全体）には制限はありません。

レポートスイートは、レポーティングにおける最も基本的なレベルのセグメントです。レポートスイートは、契約で許される限り、いくらでも設定可能です。各レポートスイートは、アドビの収集サーバー上で確保されたデータ領域を参照します。レポートスイートは JavaScript コード内の`s_account` 変数によって指定されます。

[!DNL Analytics] 内では、レポートのヘッダー右上に現在のレポートスイートが表示されます。各レポートスイートは、レポートスイート ID と呼ばれる一意の識別子を持ちます。The `s_account` variable contains one or more report suite IDs to which data is sent. このレポートスイート ID 値（[!DNL Analytics] ユーザーは見ることができない）は、使用の前にアドビから提供または承認される必要があります。すべてのレポートスイート ID には「わかりやすい名前」が関連付けられています。この名前は、[!DNL Admin Console] のレポートスイートセクションで変更することができます。

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the  variable on the HTML page, which is a common practice when the value of  may change from page to page. `s_account``s_account`Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. 場合によっては、の値も112.2o7.net `s_account` より前のドメインに表示されることがあります。 パスの値が、送信先レポートスイートを決定する唯一の値です。次のボールドテキストは、デバッガーに表示される、データの送信先であるレポートスイートを示しています。詳しくは、 [DigitalPulse Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## 構文と可能な値

レポートスイート ID は、ASCII 文字の英数字文字列であり、40 バイト以下で指定する必要があります。使用できる英数字以外の文字はハイフンだけです。スペース、ピリオド、コンマ、その他の句読点は使用できません。Folio Builder`s_account` 変数には、複数のレポートスイートを含めることができ、すべてのレポートスイートがページからデータを受け取ります。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

のすべての値は、ア `s_account` ドビが提供または承認する必要があります。

## 例

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## Analytics での変数の設定

各レポートスイート ID に関連付けられているわかりやすい名前は、Adobe [!DNL Customer Care] によって変更できます。このわかりやすい名前は、[!DNL Analytics] の画面右上に表示されます。

## 注意事項、質問、ヒント

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. 送信先レポートスイートを確認する場合は、[!DNL DigitalPulse Debugger] を使用してください。

* 場合によっては、[!DNL VISTA] を使用して送信先レポートスイートを変更することができます。ファーストパーティ cookie を使用する場合、またはサイトに 20 を超えるアクティブなレポートスイートがある場合は、[!DNL VISTA] を使用して別のレポートスイートにデータを再ルーティングまたはコピーすることを推奨します。

* Always declare `s_account` inside the JS file or just before it is included.
