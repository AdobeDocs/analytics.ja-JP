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


# browserHeight

 変数は、ブラウザーウィンドウの高さを自動取得します。


<!-- 
browserheight.xml
-->

この変数は、ページコードが開始されてから *`doPlugins`* が実行されるまでの間に設定されます。

> [!NOTE]この変数は読み取り専用です。設定しないでください。

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

**パラメーター**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> クエリパラメーター </th> 
   <th class="entry"> 値 </th> 
   <th class="entry"> 例 </th> 
   <th class="entry"> 影響を受けるレポート </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>正の整数 </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>トラフィック／技術／ブラウザーの高さ </p> </td> 
  </tr> 
 </tbody> 
</table>

