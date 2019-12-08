---
description: 指標の計算には、標準、パーティシペーション、最新、線形配分の各メソッドが使用されます。各メソッドで使用する式に基づき、値の計算方法が異なります。
title: 指標の計算
topic: Metrics
uuid: 2af58f1e-12c5-4828-ae39-c9aeaef6b705
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 指標の計算

指標の計算には、標準、パーティシペーション、最新、線形配分の各メソッドが使用されます。各メソッドで使用する式に基づき、値の計算方法が異なります。

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標計算 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> オリジナル </td> 
   <td colname="col2"> <p>成功イベントに関連付けられている最初の変数値にフルクレジットが付与されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最新 </td> 
   <td colname="col2"> <p>成功イベントに関連付けられている最後の変数値にフルクレジットが付与されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 線形 </td> 
   <td colname="col2"> <p>線形配分が選択されている場合、その訪問で表示されたすべての変数値に均等に成功イベントが配分されます。次のような数値イベントと通貨イベント<span class="term">売上高</span>などの数値イベントや通貨イベントの場合、金額を配分します。<span class="term">注文件数</span>などのカウンターイベントの場合、訪問の各変数値にイベントの一部が与えられます。レポートでは、これらの端数は合計され、最も近い整数に丸められます。 </p> <p>例えば、成功イベントの前に 4 つのページが訪問された場合、各ページにはイベントの 25％のクレジットが配分されます。同じ訪問で<span class="varname">キャンペーン</span>に 2 つの値がある場合、各キャンペーンの値にイベントの 50％のクレジットが付与されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> パーティシペーション </td> 
   <td colname="col2"> <p>訪問中における成功イベントに貢献している各変数値にフルクレジットを割り当てます。クロス訪問パーティシペーション指標を使用する場合、この計算は訪問者セッションにも適用されます。 </p> <p>詳しくは、<a href="/help/components/c-variables/c-metrics/metrics-participation.md"  >パーティシペーション</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 指標計算の例 {#section_4CE01DA35108418D9909823A7ECC4B45}

サイトでコンバージョン変数（eVar）を使用して内部検索を追跡しているとします。訪問者が $100 の購入をする前に内部検索を数回実行しました。

*`Pet`* &gt; *`Feline`* &gt; *`Cat`* &gt; *`Kitten`* &gt; $100 の購入

レポートでのクレジットの配分は次のようになります。

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar 値 </th> 
   <th colname="col2" class="entry"> 最初 </th> 
   <th colname="col3" class="entry"> 最後 </th> 
   <th colname="col4" class="entry"> 線形 </th> 
   <th colname="col5" class="entry"> パーティシペーション </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ペット </p> </td> 
   <td colname="col2"> <p>$100 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネコ科 </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ネコ </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>子ネコ </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$100 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
 </tbody> 
</table>

