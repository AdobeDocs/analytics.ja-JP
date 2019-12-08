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



# linkName

変数は[!UICONTROL リンクトラッキング]に使用されるオプションの変数で、カスタムリンク、ダウンロードリンクまたは離脱リンクの名前を決定します。


<!-- 

linkName.xml

 -->

*`linkName`* 変数は、*`tl()`* 関数の 3 番目のパラメーターで置き換えられるので、通常は必要ありません。

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> pev2 </td> 
   <td> <p>ファイルのダウンロード数 </p> <p>カスタムリンク </p> <p>離脱リンク </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL カスタムリンク]はトラッキングデータを送信するリンクを参照します。Folio Builder *`linkName`* 変数（または *`tl()`* 関数の 3 番目のパラメーター）は、[!UICONTROL カスタム]レポート、[!UICONTROL ダウンロード]レポートまたは[!UICONTROL 離脱リンク]レポートに表示される値を特定します。*`linkName`* が入力されていない場合、リンクの URL がレポートに表示されます。

**構文と可能な値** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

標準の変数の制限以外、*`linkName`* に対する制限はありません。

**例** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**設定** {#section_F15FF429FC274F708D50DF79D4668EA3}

なし

**注意事項、質問、ヒント** {#section_170A78452A7340B5B229713AC1FB71FA}

* *`linkName`*&#x200B;変数は、*`tl()`* 関数の 3 番目のパラメーターで置き換えられます。

* *`linkName`* 変数と *`tl()`* 関数の 3 番目のパラメーターが空白の場合、リンクが相対リンクの場合でも、リンクの完全修飾 URL がレポートに表示されます（クエリ文字列は除く）。
