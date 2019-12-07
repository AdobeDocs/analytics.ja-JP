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


# pageType

 変数は、404（ページが見つかりません）エラーページを指定する目的でのみ使用します。


<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
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
   <td> 20 バイト </td> 
   <td> pageType </td> 
   <td> パス／ページ／ページが <p>見つかりません </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. 次に示すように、エラーページで *`pageType`* 変数を設定します。

404 エラーページではページ名変数を使用しないでください。Folio Builder *`pageType`* 変数は、404 エラーページにのみ使用されます。

ほとんどの場合、404 エラーページはハードコードされた静的なページです。このような場合、.JS ファイルへの参照が適切な絶対または相対パス／ディレクトリに設定されていることが重要です。

**構文と可能な値** {#section_C1C59968226446559B05F6EE7374D525}

次に示すように、*`pageType`* の唯一の許可値は「errorPage」です。

```js
s.pageType="errorPage"
```

**例** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**設定** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

なし

**注意事項、質問、ヒント** {#section_943681AB01FE47BEAC72E93CB60C53C8}

その他のサーバーサイドエラー（ エラーなど）を取り込むには、prop を使用してエラーメッセージを取り込み、「`500 Error: <URL>`」などと設定します。この `<URL>` は、*`pageName`* 変数内で要求された URL です。この一連の操作に従うことで、[!UICONTROL パス]レポートを使用して、500 エラーの発生原因となったパスを確認することができます。prop によって、サーバーからどのエラーメッセージが提示されたかがわかります。

