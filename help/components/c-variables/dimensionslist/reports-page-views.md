---
description: 指定された期間（時間、日、週、月、四半期、年）に Web サイトのページが閲覧された回数を表示するトレンドレポートです。このレポートでは、サイトの各ページのページビュー数と、サイト全体のページビュー合計数を追跡できます。
title: ページビュー数
topic: Reports
uuid: c78260c6-9ad4-4b85-84fd-763627392e44
translation-type: tm+mt
source-git-commit: 707b61d853a8ec68b3f77a35a1aa5f0c7dd8a1fd

---


# ページビュー数

指定された期間（時間、日、週、月、四半期、年）に Web サイトのページが閲覧された回数を表示するトレンドレポートです。このレポートでは、サイトの各ページのページビュー数と、サイト全体のページビュー合計数を追跡できます。

[ページビュー](/help/components/c-variables/c-metrics/metrics-page-view.md)は画像やビデオなどのページの要素ではなく、ドキュメントの全ページに対する要求です。例えば、1 名の訪問者が 1 回の訪問中に 15 ページ閲覧すると、15 ページビューとカウントされます。1 名の訪問者が 1 回の訪問中に同じページを 3 回閲覧すると、3 ページビューとカウントされます。

## レポートのプロパティ

* This report references the number of times the [`t()`](/help/implement/vars/functions/t-method.md) method is called on your site.
* このメソッドを使用するリンクトラッキ [`tl()`](/help/implement/vars/functions/tl-method.md) ング呼び出しは、このレポートではカウントされません。
* ユーザーがページを更新したり戻るボタンをクリックしたりするとイメージリクエストが送信されるため、これらのアクションもこのレポートに含まれます。
* 時間別の分類はレポートスイートのタイムゾーンに基づいています。
* このレポートには行項目は含まれていません。そのため、このレポートはトレンドフォーマットでのみ表示できます。
* 時間、日、週、月、四半期、および年の精度を適用できます。使用可能な精度はレポート日付の範囲に応じて異なります。

## 製品固有の情報

<table id="table_61F964F47D1D43508B271999F495F7F9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> サイトコンテンツ</span>／<span class="uicontrol">ページビュー数</span> </p> <p>このレポートではセグメントを使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad hoc analysis </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DB66B8F9F6BF473A83EC7668F59776D0"> 
     <li id="li_D1CB486058F040859560D5BFDF3972EE"> 他のすべてのレポートと変数によってこのレポート内の各項目を分類し、任意の精度で分類を表示できます。 </li> 
     <li id="li_BAADA9ADDD6F47B08D129FD30CD8EF2E">このレポート内にあるコンバージョンとトラフィックの指標と共に、すべてのコンバージョン指標に関する様々な配分を使用できます。 </li> 
     <li id="li_3696CA6E0BD54305B3609CCC80F851BA">このレポートでは複数の高度なアドバンスセグメントを使用できます。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

