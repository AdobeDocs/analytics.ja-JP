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


# pageURL

 変数は、ページの実際の URL よりも優先されます。


<!-- 

pageURL.xml

 -->

まれに、ページの URL が Analytics でレポートしたい URL ではないことがあります。

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 無制限* </td> 
   <td> <p>g </p> </td> 
   <td> トラフィック／セグメント化／最頻訪問ページ、パス </td> 
   <td> ページ URL </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE]アドビでは *`pageURL`* には最大 64 KB の値を指定できますが、一部のブラウザーでは、イメージリクエストの URL に対してサイズの制限が適用されます。その他のデータが切り捨てられないように、255 バイトを超えるページ URL は分割され、最初の 255 バイトは `g=` パラメーターに、残りのバイトはその後のクエリ文字列の `-g=` クエリパラメーターに表示されます。

**構文と可能な値** {#section_22AF3BF7C2F743549967B0C760A095C0}

*`pageURL`* 変数は、プロトコルを含む有効な URL である必要があります。ドメインは、レポートに入力される前に強制的に小文字表示になり、クエリ文字列は、Analytics の設定に応じて削除される場合があります。

```js
s.pageURL="proto://domain/path?query_string"
```

URL と互換性のある文字のみページ URL として許可されます。

> [!NOTE]ｖカスタム目的で *`pageURL`* 変数を使用する前に、アドビのコンサルタントまたはカスタマーケアにお問い合わせいただくことを強くお勧めします。

**例** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**設定** {#section_A8F77DAD88164528ACC5C16C066B47DF}

なし

