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


# referrer

 変数は、失われたリファラー情報を復元するために使用できます。


<!-- 

referrer.xml

 -->

サーバーサイドと JavaScript のリダイレクトは、訪問者を正しい場所にルーティングするためによく使用されます。ただし、ブラウザーがリダイレクトされると、元の参照 URL は失われます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 255 バイト | R | トラフィック／検索方法、コンバージョン／検索方法 | document.referrer |

多くの企業では、Web サイト内の多数の場所でリダイレクトを使用します。例えば、訪問者を検索エンジンの有料検索結果からのリダイレクト経由で送信します。ブラウザーがリダイレクトされると、リファラーは多くの場合失われます。Folio Builder *`referrer`* 変数は、リダイレクト後に最初のページの元の *`referrer`* 値を復元するために使用できます。*`referrer`* はサーバーサイドで、または JavaScript を使用してクエリ文字列から指定することができます。

Analytics でリファラーを記録するには、リファラーが「整形式」であることが必要です。つまり、標準の URL 形式に従っており、プロトコルと適切な場所を含んでいる必要があります。

**構文と可能な値** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

 *`referrer`* には URL 互換値のみを使用してください。文字列が URL エンコード（スペースなし）されていることを確認します。

**例** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**設定** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

なし

**注意事項、質問、ヒント** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

*`referrer`* は標準の URL と類似しており、プロトコルを含んでいる必要があります。
