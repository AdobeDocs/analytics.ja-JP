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


# 郵便番号

state 変数と zip 変数はコンバージョン変数です。


<!-- 

zip.xml

 -->

これらの変数は、イベントを取り込む点で eVar と同様ですが、eVar とは異なり永続的ではありません。Folio Builder *`zip`* および *`state`* 変数は、すぐに期限が切れる eVar のように機能します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 50 バイト | 郵便番号 | コンバージョン／訪問者プロファイル／郵便番号 | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. 例えば、郵便番号別のコンバージョン率を比較するために *`zip`* を使用している場合、チェックアウトプロセスの各ページに *`zip`* を挿入する必要があります。アドビでは、郵便番号のソースとして請求先住所を使用することを推奨します。代わりに、配送先住所を選択することもできます（注文の配送先住所が 1 つだけである場合）。メディアサイトでは、登録および広告クリックスルートラッキングのために、*`zip`* や *`state`* を使用することもできます。

**構文と可能な値** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

*`zip`* 変数には、値やフォーマットの制限はありません。標準の変数の制限以外、*`zip`* に対する制限はありません。

**例** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**設定** {#section_7987084EECC34DD38B643B94F82385CA}

なし

**注意事項、質問、ヒント** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* [!UICONTROL zip] は、関連イベントが発生するすべてのページ（チェックアウトプロセスの各ページなど）に設定します。
* *`zip`* 変数と **`state` 変数は、ページビューで期限切れになる eVars のように機能します。

