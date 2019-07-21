---
description: 指定期間内の Web サイト全体への訪問件数を表示します。
seo-description: 指定期間内の Web サイト全体への訪問件数を表示します。
seo-title: 訪問回数
solution: Analytics
title: 訪問回数
topic: レポート
uuid: ff65bddf- fb65-4cf0-8aae-4ab59c2bb0a7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 訪問回数

指定期間内の Web サイト全体への訪問件数を表示します。

**レポートプロパティ**

* 1 回の訪問は、30 分を超える無操作状態または 12 時間を超える継続的な操作状態のない、連続したページビューの進行として定義されています。
* 訪問の有効期限が切れると、後続のイメージリクエスト発生時に新規の訪問が開始します。
* 1 人の訪問者には、通常は最低 1 回（おそらくは複数回）の訪問が含まれます。
* 訪問の先頭部分は、新規訪問者による最初のイメージリクエスト、または既存ユーザーの訪問の有効期限が切れた後の最初のイメージリクエストです。これは入口ページとして識別できます。
* 訪問の末尾部分は、訪問の有効期限が切れる前の最後のイメージリクエストです。これは入口ページとして識別できます。

   詳しくは、 [入口および出口レポート](../../../components/c-variables/dimensionslist/reports-entries-exits.md#concept_C4AED2C1D62E43A48ACAA837327FCCF2).
* 時間別の分類はレポートスイートのタイムゾーンに基づいています。
* このレポートには行項目は含まれていません。これはトレンドフォーマットでのみ表示されます。
* 時間、日、週、月、四半期、および年の精度を適用できます。これらの精度設定はレポートの日付範囲に応じて使用できます。

詳しくは、[訪問指標](../../../components/c-variables/c-metrics/metrics-visit.md#concept_9DA4D9EF8B964755BAC57378AD37911E)を参照して、Experience Cloud でこの指標がどのように処理されるかを確認してください。

**製品固有のレポート情報**

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 製品 </th> 
   <th colname="col2" class="entry"> ナビゲーション </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> サイト指標</span>／<span class="uicontrol">訪問回数</span> </p> <p>選択したページに関する<span class="wintitle">訪問回数レポート</span>を実行できます。午前 0 時にまたがる訪問は、訪問が開始した日と終了した日の両方でカウントされます。ただし、指定された日付範囲についての合計は重複除外されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> レポート</span>／<span class="uicontrol">サイト指標</span>／<span class="uicontrol">訪問回数</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> 他のほぼすべてのレポートと変数によってこのレポート内の各項目を分類し、任意の精度で分類を表示できます。 </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">午前 0 時にまたがる訪問は、訪問が開始した日と終了した日の両方でカウントされます。ただし、指定された日付範囲についての合計は重複除外されます。 </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">このレポート内にあるコンバージョンとトラフィックの指標と共に、すべてのコンバージョン指標に関する様々な配分を使用できます。 </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">このレポートでは複数の高度なアドバンスセグメントを使用できます。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

