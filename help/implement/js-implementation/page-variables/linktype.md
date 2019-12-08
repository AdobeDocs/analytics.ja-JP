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



# linkType

 変数はリンクトラッキングで使用されるオプションの変数で、リンク名や URL が表示されるレポート（カスタムリンク、ダウンロードリンクまたは離脱リンク）を決定します。


<!-- 

linkType.xml

 -->

*`linkType`* 変数は、*`tl()`* 関数の 2 番目のパラメーターで置き換えられるので、通常は必要ありません。

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
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
   <td> 1 文字 </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>ファイルのダウンロード数 </p> <p>カスタムリンク </p> <p>離脱リンク </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

カスタムリンクはデータを Analytics に送信します。*`linkType`* 変数（または、*`tl()`* 関数の 2 番目のパラメーター）は、リンク名または URL が表示されるレポート（[!UICONTROL カスタム]、[!UICONTROL ダウンロード]、または[!UICONTROL 離脱リンク]レポート）を特定するために使用されます。

離脱リンクとダウンロードリンクの場合、クリックされたリンクが離脱リンクとダウンロードリンクのどちらであるかに応じて、*`linkType`* 変数が自動的に設定されます。カスタムリンクは、この変数または *`tl()`* 関数の 2 番目のパラメーターを使用して、3 つのレポートのいずれかにデータを送信するよう設定できます。*`linkType`* を「o」、「e」または「d」に設定することにより、*`linkName`* またはリンク URL がそれぞれ[!UICONTROL カスタムリンク]、[!UICONTROL 離脱リンク]、または [!UICONTROL ファイルのダウンロード数]レポートに送信されます。

**構文と可能な値** {#section_18DB3A8083FB4F75B970055ED336DA4E}

*`linkType`* 変数の構文は、XML を使用するかクエリ文字列を使用するかによって変わります。

XML を使用する場合は、変数には 1 つの文字（o、e または d）のみが含まれます。

```js
s.tl(this,'o','Link Name');
```

クエリ文字列 `pe` を使用する場合は、`lnk_e`、`lnk_d` または `lnk_o` を使用する必要があります。

**例** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**設定** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

なし

**注意事項、質問、ヒント** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* *`linkType`* 指定しない場合、カスタムリンク（'o'）が想定されます。
