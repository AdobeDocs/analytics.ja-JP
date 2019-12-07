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


# pageName

 変数には、サイトの各ページの名前が含まれます。


<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
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
   <td> 100 バイト </td> 
   <td> pageName </td> 
   <td> <p>ページ </p> <p>パス </p> </td> 
   <td> ページ URL </td> 
  </tr> 
 </tbody> 
</table>

Folio Builder *`pageName`* 変数には、ビジネスユーザーにとってわかりやすい値を入力する必要があります。ほとんどの場合、*`pageName`* の値は URL やファイルのパスではありません。*`pageName`* の一般的な値には、「ホームページ」、「チェックアウト」、「ご購入ありがとうございました」、「登録」などの名前があります。

改行文字、em ダッシュ（長いダッシュ）、en ダッシュ（短いダッシュ）または HTML 文字が、ページ名やその他の変数に使用されないように注意してください。改行文字を送信するブラウザーもありますが、送信しないブラウザーもあります。これにより、Analytics のデータが、外見上は同じ 2 つのページ名に分割される場合があります。多くの Office アプリケーションや電子メールクライアントでは、入力時にハイフンが自動的に en ダッシュまたは em ダッシュに変換されます。en ダッシュおよび em ダッシュは Analytics 変数では無効な文字なので（127 以上のコードの ASCII 文字）、Analytics では無効な文字を含むページ名が記録されず、代わりに URL が表示されます（日本語を有効化したレポートスイートを除く）。

*`pageName`* が空白の場合、ページ名を表すために URL が使用されます。*`pageName`* が空白のままになっていると、問題が発生することがあります。これは、1 つのページに対する URL が必ずしも同じではない場合があるからです（`www.mysite.com` と `mysite.com` は同じページですが URL は異なります）。

**構文と可能な値** {#section_7A61EE70F1A84D26B414404998C84BA8}

*`pageName`* 変数には、Analytics のビジネスユーザーに役立つ識別子を含める必要があります。

```js
s.pageName="page_name"
```

標準の変数の制限以外、*`pageName`* に対する制限はありません。

**例** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**設定** {#section_58CBC68C805344A999EB47455FEBA8D5}

管理者は、[!UICONTROL ページに名前を付ける]ツールを使用して Analytics でのページの表示名を変更することができますが、このツールによって問題が発生する可能性があり、レポートに悪影響が出る場合があります。ページに名前を付けるツールを使用するには、アドビ[!UICONTROL カスタマーケア]にお問い合わせください。

**注意事項、質問、ヒント** {#section_BB41DC9682C34385B9CAA80D5257C113}

*`pageName`* に不正な文字が含まれていないことを確認してください。
