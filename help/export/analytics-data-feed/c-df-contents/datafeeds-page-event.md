---
description: page_event の値に基づいてヒットタイプを判別する参照テーブル。
keywords: データフィード;ページ;event;page_ event;post_ page_ event
seo-description: page_event の値に基づいてヒットタイプを判別する参照テーブル。
seo-title: ページイベント参照
solution: Analytics
title: ページイベント参照
topic: Reports and Analytics
uuid: 73af597c-5560-466e-94b2- ddd1d64797c8
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# ページイベント参照

page_event の値に基づいてヒットタイプを判別する参照テーブル。

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ヒットタイプ </th> 
   <th colname="col02" class="entry"> page_event の値 </th> 
   <th colname="col2" class="entry"> post_page_event の値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ページビュー </td> 
   <td colname="col02"> post と同じ </td> 
   <td colname="col2"> <p>0 の場合、すべてのページビュー（<code>s.t()</code> コール） </p> <p>0 の場合、モバイル SDK からの <code>trackState</code> コール </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リンクトラッキング </td> 
   <td colname="col02"> <p>10 の場合、「その他のリンク」 </p> <p>10 の場合、モバイル SDK からの <code>trackAction</code> コールおよびライフサイクルコール </p> <p>11 の場合、「ダウンロードリンク」 </p> <p>12 の場合、「外部リンクまたは離脱リンク」 </p> </td> 
   <td colname="col2"> <p>100 の場合、「その他のリンク」 </p> <p>100 の場合、モバイル SDK からの <code>trackAction</code> コールおよびライフサイクルコール </p> <p>101 の場合、「ダウンロードリンク」 </p> <p>102 の場合、「外部リンクまたは離脱リンク」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> マイルストーンビデオ </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 – メディア開始イベント </p> <p>32 - メディアの更新のみのイベント（eVarまたはその他の変数処理を実行しません） </p> <p>33 – メディアと他の変数の更新イベント（eVar その他の変数処理を含む） </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76 – メディア開始イベント </p> <p>77 – メディアの更新のみのイベント（eVar その他の変数処理を実行しない） </p> <p>78 – メディアと他の変数の更新イベント（eVar その他の変数処理を含む） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ハートビートビデオ </p> </td> 
   <td colname="col02"> post と同じ </td> 
   <td colname="col2"> <p> 50 = （Adobe Primetime 以外の）メディアストリーム開始 </p> <p> 51 = （Adobe Primetime 以外の）メディアストリーム終了（完了） </p> <p> 52 = （Adobe Primetime 以外の）メディアストリームスクラブ </p> <p> 53 = （Adobe Primetime 以外の）メディアストリームキープアライブ </p> <p> 54 = （Adobe Primetime 以外の）メディアストリーム広告開始 </p> <p> 55 = （Adobe Primetime 以外の）メディアストリーム広告終了（完了） </p> <p> 56 = （Adobe Primetime 以外の）メディアストリーム広告スクラブ </p> <p> 60 = Primetime のメディアストリーム開始 </p> <p> 61 = Primetime のメディアストリーム終了（完了） </p> <p> 62 = Primetime のメディアストリームスクラブ </p> <p> 63 = Primetime のメディアストリームキープアライブ </p> <p> 64 = Primetime のメディアストリーム広告開始 </p> <p> 65 = Primetime のメディアストリーム広告終了（完了） </p> <p> 66 = Primetime のメディアストリーム広告スクラブ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 調査 </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Target の分析 </td> 
   <td colname="col02"> 70 - Target アクティビティデータを含むヒットを示します。Analytics 呼び出しに関連するヒットおよび関連しないヒットの 70 です。 </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

