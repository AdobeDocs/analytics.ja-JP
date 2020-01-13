---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.useForcedLinkTracking


 変数は、データの保存とレポートをおこなうレポートスイートを決定します。

複数のレポートスイート（複数スイートタギング）に送信している場合、`s.account` は値のコンマ区切りリストになることがあります。レポートスイート ID はアドビが決定します。

## パラメーター

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 40 バイト | In the URL path | 該当なし | 該当なし |

各レポートスイート ID は、[!DNL Admin Console] で作成された値と一致している必要があります。各レポートスイート ID は 40 バイト以下にする必要がありますが、すべてのレポートスイートの合計（コンマ区切りリスト全体）には制限はありません。

レポートスイートは、レポーティングにおける最も基本的なレベルのセグメントです。レポートスイートは、契約で許される限り、いくらでも設定可能です。各レポートスイートは、アドビの収集サーバー上で確保されたデータ領域を参照します。レポートスイートは JavaScript コード内の`s_account` 変数によって指定されます。

[!DNL Analytics] 内では、レポートのヘッダー右上に現在のレポートスイートが表示されます。各レポートスイートは、レポートスイート ID と呼ばれる一意の識別子を持ちます。`s_account` 変数には、データが送信される 1 つ以上のレポートスイート ID が含まれます。このレポートスイート ID 値（[!DNL Analytics] ユーザーは見ることができない）は、使用の前にアドビから提供または承認される必要があります。すべてのレポートスイート ID には「わかりやすい名前」が関連付けられています。この名前は、[!DNL Admin Console] のレポートスイートセクションで変更することができます。

`s_account` 変数は、通常、JavaScript ファイル（s_code.js）内で宣言されます。`s_account`変数は HTML ページで宣言できます。これは、`s_account` の値がページごとに変わる場合の一般的な方法です。`s_account` 変数はグローバルスコープなので、アドビの JavaScript ファイルを含める直前に宣言する必要があります。`s_account` に値が含まれていない場合、データは [!DNL Analytics] に送信されません。

アドビの [!DNL DigitalPulse Debugger]には、`s_account` の値が表示されます。この値は、「Image」という語句のすぐ下、/b/ss/ の直後に示されます。場合によっては、`s_account` の値もドメイン（112.2o7.net より前）に表示されることがあります。パスの値が、送信先レポートスイートを決定する唯一の値です。次のボールドテキストは、デバッガーに表示される、データの送信先であるレポートスイートを示しています。詳しくは、「[DigitalPulse Debugger](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/testing-and-validation/debugger.html)」を参照してください。

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## 構文と可能な値

レポートスイート ID は、ASCII 文字の英数字文字列であり、40 バイト以下で指定する必要があります。使用できる英数字以外の文字はハイフンだけです。スペース、ピリオド、コンマ、その他の句読点は使用できません。`s_account` 変数には、複数のレポートスイートを含めることができ、すべてのレポートスイートがページからデータを受け取ります。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

`s_account` のすべての値は、アドビが提供または承認する必要があります。

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

* `s_account` が空の場合、宣言されていない場合、または予期しない値が含まれている場合、データは収集されません。
* `s_account` 変数をコンマ区切りリスト（マルチスイートタギング）で複数指定する場合、レポートスイート ID の間にスペースを挿入しないでください。
* [!UICONTROL s.dynamicAccountSelection] が「*True*」に設定されている場合は、URL を使用して送信先レポートスイートが決定されます。送信先レポートスイートを確認する場合は、[!DNL DigitalPulse Debugger] を使用してください。

* 場合によっては、[!DNL VISTA] を使用して送信先レポートスイートを変更することができます。ファーストパーティ cookie を使用する場合、またはサイトに 20 を超えるアクティブなレポートスイートがある場合は、[!DNL VISTA] を使用して別のレポートスイートにデータを再ルーティングまたはコピーすることを推奨します。

* `s_account` は常に JS ファイル内、または JS ファイルが含まれる直前に宣言します。
