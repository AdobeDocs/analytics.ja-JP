---
description: 以下の表に、データ収集に送られる各 Analytics 変数の値が含まれるクエリパラメーターを示します。
keywords: Analytics Implementation
title: データ収集クエリパラメーター
topic: Developer and implementation
uuid: 4d5af486-df27-42fe-bb9c-28938dddf2b2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# データ収集クエリパラメーター

以下の表に、データ収集に送られる各 Analytics 変数の値が含まれるクエリパラメーターを示します。

ここに示す情報は、[パケットアナライザー](/help/implement/impl-testing/packet-monitor.md)を使用してデバッグするとき、手動でイメージリクエストを作成するとき、さらに.[動的変数](/help/implement/js-implementation/c-variables/dynvars-overview.md)を使用するときに役に立ちます。

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> パラメーター </th> 
   <th class="entry"> Analytics 変数 </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> なし </td> 
   <td colname="col3"> なし </td> 
   <td colname="col4"> Audience Manager のロケーションヒント（Experience Cloud 共有プロファイルの統合で使用） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> なし </td> 
   <td colname="col3"> なし </td> 
   <td colname="col4"> Audience Manager Blob（Experience Cloud 共有プロファイルの統合で使用） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> なし </td> 
   <td colname="col3"> なし </td> 
   <td colname="col4"> Analytics 訪問者 ID </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> イメージリクエストの開始を示します。 </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> なし </td> 
   <td> なし </td> 
   <td> イメージリクエストの終了を示します。これは、要求が切り捨てられていないことを表しています。 </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | ブラウザーの高さ </td> 
   <td> ブラウザーウィンドウの高さ（ピクセル） </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | ブラウザーの幅 </td> 
   <td> ブラウザーウィンドウの幅（ピクセル） </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> なし </td> 
   <td> 訪問者プロファイル | テクノロジー | 画面の色 </td> 
   <td> カラー画像画質（ビット） </td> 
  </tr> 
  <tr> 
   <td> </td><td><p></p></td><td><p></p></td><td><p></p><p><code> &lt;my.a&gt;red&lt;/my.a&gt; </code></p><p></p><p><code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code></p><p><code> my.a = red </code></p><p><code> c.&my.a=red </code></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td><code> D </code></td><td></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p><code> t </code></p><code>
      dd/mm/yyyy&amp;nbsp;hh:mm:ss&amp;nbsp;D&amp;nbsp;OFFSET 
    </code><p><code> 0-6 </code><code> OFFSET </code></p><code>
      offset&amp;nbsp;from&amp;nbsp;GMT&amp;nbsp;in&amp;nbsp;hours&amp;nbsp;*&amp;nbsp;60&amp;nbsp;*&amp;nbsp;-&amp;nbsp;1 
    </code><p></p><code>
      23/09/2016&amp;nbsp;14:00:00&amp;nbsp;1&amp;nbsp;420 
    </code></td></tr><tr><td><code> ts </code></td><td><p></p></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td><p></p></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p></p></td></tr></tbody></table>

