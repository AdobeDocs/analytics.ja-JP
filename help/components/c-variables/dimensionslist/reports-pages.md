---
description: トラフィックの多い順にページを一覧表示します。ページの量的データに関するものであれば、必要な指標を追加することでこのレポートを使ってその情報を得ることができます。
seo-description: トラフィックの多い順にページを一覧表示します。ページの量的データに関するものであれば、必要な指標を追加することでこのレポートを使ってその情報を得ることができます。
seo-title: ページ
solution: Analytics
title: ページ
topic: レポート
uuid: 6435e262- e734-4c15- af5b-173799d5cc43
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ページ

トラフィックの多い順にページを一覧表示します。必要情報がページの量的データに関するものであれば、必要な指標を追加することでこのレポートを使ってその情報を得ることができます。

## 配分、有効期限および特別な値 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

Reports &amp; Analytics の場合、ページレポートの指標では線形配分を使用します。例えば、売上高は、購入イベント前に表示されたすべてのページ間で分割されます。買い物かごへの追加など、1 ページでしか発生しないと予想されるいくつかの指標に関して混乱を引き起こす可能性があります。

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">Reports &amp;  <p>Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 指標配分 </td> 
   <td colname="col2"> 線形 </td> 
   <td colname="col3"> 配分は、ディメンションによって異なります。デフォルトでは、ラストタッチ配分が使用されますが、「pagename」ディメンションは例外です。カスタムイベントを「pagename」に適用すると、正確なヒット配分が使用されます。 </td> 
   <td colname="col4"> <p>同じページ表示に設定された値 </p> </td> 
   <td colname="col5"> <p>同じページ表示に設定された値 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 有効期限 </td> 
   <td colname="col2"> ページ表示 </td> 
   <td colname="col3"> ページ表示 </td> 
   <td colname="col4"> ページ表示 </td> 
   <td colname="col5"> ページ表示 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 値の制限 </td> 
   <td colname="col2"> <p>1 ヶ月あたり最初の 500,000 件のユニーク値とトラフィックに関する新しい値 </p> </td> 
   <td colname="col3"> <p>1 ヶ月あたり最初の 500,000 件のユニーク値とトラフィックに関する新しい値 </p> </td> 
   <td colname="col4"> なし </td> 
   <td colname="col5"> <p>1 ヶ月あたり最初の 500,000 件のユニーク値とトラフィックに関する新しい値 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特別な値 </td> 
   <td colname="col2"> <p>（低トラフィック）は、受け取るトラフィックが少量でレポートされない、最初の 500,000 件を超過した値を表します。 </p> </td> 
   <td colname="col3"> <p>（低トラフィック）は、受け取るトラフィックが少量でレポートされない、最初の 500,000 件を超過した値を表します。 </p> </td> 
   <td colname="col4"> なし </td> 
   <td colname="col5"> <p>（低トラフィック）は、受け取るトラフィックが少量でレポートされない、最初の 500,000 件を超過した値を表します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Reports &amp; Analytics では、ページレポートでカスタムイベントを指標として適用すると、線形配分が使用されます。

これはつまり、カスタムイベントが s.tl() 呼び出しで送信されても、以前の s.tl() 呼び出しの線形配分が使用されるということです。例：

| ページ名 | Page_event | イベント |
|---|---|---|
| Page1 | **s.t()** |  |
| Page1 | s.tl() | Event1 |
| Page1 | s.tl() | Event1 |
| Page1 | s.tl() | Event1 |
| Page2 | **s.t()** |  |
| Page2 | **s.t()** |  |
| Page2 | s.tl() | Event1 |

このシナリオの場合、ページレポートでの配分は次のようになります。

| ページ | ページビュー数 | イベント 1 |
|---|---|---|
| ページ 1 | 1 | 1+1+1+1/3 = 3.33 |
| ページ 2 | 2 | 2/3 = 0.67 |

イベントが s.tl 呼び出しで送信される場合でも、送信されたイベント（s.t() 呼び出し）の前に表示されたページには、一部のクレジットのみが割り当てられます。

## メモ {#section_47B0F4746D4847AC9E8697127063F4D0}

* ページが存在しない場合は、URL が使用されます。
* ページ名、ページ URL またはイベントリスト（コマースイベントなし）のないヒットは除外されます。
* ページの分類は、永続的な値を持つすべてのページを表示します。

