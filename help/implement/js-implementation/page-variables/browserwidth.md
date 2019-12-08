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



# browserWidth

 変数は、ブラウザーウィンドウの幅を自動取得します。


<!-- 

browserwidth.xml

 -->

この変数は、ページコードが開始されてから *`doPlugins`* が実行されるまでの間に設定されます。

> [!NOTE]この変数は読み取り専用です。設定しないでください。

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

**パラメーター**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>クエリパラメーター</b> </p> </td> 
   <td> <p> <b>値</b> </p> </td> 
   <td> <p> <b>例</b> </p> </td> 
   <td> <p> <b>影響を受けるレポート</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>正の整数 </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>トラフィック／技術／ブラウザーの幅 </p> </td> 
  </tr> 
 </tbody> 
</table>
