---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# state

state 変数と zip 変数はコンバージョン変数です。


<!-- 

state.xml

 -->

これらの変数は、イベントを取り込む点で eVar と同様ですが、eVar とは異なり永続的ではありません。Folio Builder *`zip`* および *`state`* 変数は、すぐに期限が切れる eVar のように機能します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 50 バイト | state | コンバージョン／訪問者プロファイル／訪問者の州 | "" |

*`state`* 変数と *`zip`* 変数はすぐに期限切れになるので、変数に関連付けられるイベントは、これらの変数が入力されているページと同じページで発生するイベントだけです。例えば、州別のコンバージョン率を比較するために *`state`* 使用している場合、チェックアウトプロセスの各ページに *`state`* 変数を挿入する必要があります。コンバージョンサイトでは、郵便番号のソースとして請求先住所の使用を推奨しますが、代わりに届け先住所を選択することもできます（注文の届け先住所が 1 つだけである場合）。メディアサイトでは、登録および広告クリックスルートラッキングのために、*`zip`* や *`state`* を使用することもできます。

**構文と可能な値** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

*`state`* 変数には、特別な値やフォーマットの制限はありません。標準の変数の制限以外、*`state`* に対する制限はありません。

**例** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**設定** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

なし

**注意事項、質問、ヒント** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* *`state`* は、関連イベントが発生するすべてのページ（チェックアウトプロセスの各ページなど）に設定します。
* *`zip`* 変数と **`state` 変数は、ページビューで期限切れになる eVars のように機能します。
