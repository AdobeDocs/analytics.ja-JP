---
description: 訪問者がどのドメインや URL から Web サイトに来訪したか、訪問者が Web サイトをどのような方法で見つけたか、およびこれらの参照場所から Web サイトへの訪問回数が表示されます。
seo-description: 訪問者がどのドメインや URL から Web サイトに来訪したか、訪問者が Web サイトをどのような方法で見つけたか、およびこれらの参照場所から Web サイトへの訪問回数が表示されます。
seo-title: リファラー
solution: Analytics
title: リファラー
topic: レポート
uuid: e63b47b4-49f3-43af-8409-3272bas0484e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# リファラー

訪問者がどのドメインや URL から Web サイトに来訪したか、訪問者が Web サイトをどのような方法で見つけたか、およびこれらの参照場所から Web サイトへの訪問回数が表示されます。

例えば、訪問者がサイト A からリンクをクリックしてサイトに来訪した場合、ドメインの一部として定義されていない限り、サイト A がリファラーとなります。導入時に、担当の導入コンサルタントが Web サイトの一部となるドメインや URL の定義を支援します（この変更は、導入後におこなうこともできます）。

こうした定義されたドメインおよび URL を含まないドメインや URL は、リファラーと見なされます。例えば、Web ページ A と Web ページ B が内部 URL フィルターに含まれていて、Web ページ C は含まれていないとします。この場合、Web ページ C がリファラーと見なされます。

## 配分、有効期限および特別な値 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reports &amp; Analytics（SiteCatalyst） </th> 
   <th colname="col3" class="entry"> ad hoc analysis </th> 
   <th colname="col4" class="entry"> data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 指標配分 </td> 
   <td colname="col2"> 最新 </td> 
   <td colname="col3"> 最新 </td> 
   <td colname="col4"> 最新 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 有効期限 </td> 
   <td colname="col2"> 訪問 </td> 
   <td colname="col3"> 訪問 </td> 
   <td colname="col4"> 訪問 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 値の制限 </td> 
   <td colname="col2"> 無制限（今後のリリースで変更される可能性があります） </td> 
   <td colname="col3"> 無制限（今後のリリースで変更される可能性があります） </td> 
   <td colname="col4"> なし </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特別な値 </td> 
   <td colname="col2"> <p>「なし」：訪問中にリファラーがなかったサイト全体での合計。 </p> </td> 
   <td colname="col3"> <p>「なし」：訪問中にリファラーがなかったサイト全体での合計。 </p> </td> 
   <td colname="col4"> <p> 空 - 「なし」と同じです。訪問中にリファラーがなかったサイト全体での合計。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## メモ {#section_B83A3571D64E4E7792712FAF740D7955}

* リファラー、リファラータイプおよび参照ドメインは、訪問の最初のヒット時に設定されます。リファラーが外部の場合（例えば、訪問者がサイトから出て、検索エンジンを使用して最初の訪問の有効期限が切れるまでに直前のサイトに戻った場合）は、これらの値は訪問中に設定されます。これらの値は同時に設定され、訪問間で保持されます。
* 内部 URL にはフィルターが適用されます。内部 URL フィルターと一致しないリファラーのみがこのレポートに含まれます。
* 対応する指標は ad hoc analysis ではリファラーインスタンスと呼ばれます。
* 手動入力/ブックマークの値はリファラーレポートに含まれません。つまり、サイト全体の訪問はこのレポートの訪問と一致しません。

## レポート履歴 {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日付 </th> 
   <th colname="col2" class="entry"> 変更 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2014 年 1 月 16 日 </td> 
   <td colname="col2"> data warehouse が Reports &amp; Analytics で使用されるロジックと一致するように更新されました。これまで、検索キーワードは訪問間で保持されませんでした。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2012 年 6 月 19 日 </td> 
   <td colname="col2"> <p> 2012 年 7 月まで、「なし」には、すべてのモバイルトラフィック、手動入力/ブックマークおよび JavaScript なしの訪問が含まれました。2012 年 7 月から、「なし」には、訪問の最初のページにおける JavaScript なしのヒットのみが含まれます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

