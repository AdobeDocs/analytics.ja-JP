---
description: Report Builder では、Analytics のカスタムカレンダーを使用します。このカレンダーでは、週や年の最初の日を定義したり、様々なスタイルの小売業用カレンダーを使用したりできます。カレンダーフォーマットは、販売の比較および予測の標準化、人件費の分析、実在庫のカウント規則など、様々な目的に使用されます。
title: カスタムカレンダー
topic: Report Builder
uuid: 88d24bf9-de46-41e0-937e-b8a1fe36c55d
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 91%

---


# カスタムカレンダー

Report Builder では、Analytics のカスタムカレンダーを使用します。このカレンダーでは、週や年の最初の日を定義したり、様々なスタイルの小売業用カレンダーを使用したりできます。カレンダーフォーマットは、販売の比較および予測の標準化、人件費の分析、実在庫のカウント規則など、様々な目的に使用されます。

各カレンダーフォーマットについて次に説明します。

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> カレンダー </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>グレゴリオ暦カレンダー </p> </td> 
   <td colname="col2"> <p> 通常のカレンダーフォーマットです（1 月から 12 月まで、1 ヶ月の日数は 30 日または 31 日で月ごとに週数が異なる）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>修正グレゴリオ暦カレンダー </p> </td> 
   <td colname="col2"> <p> グレゴリオ暦カレンダーですが、年の最初の月と週の最初の日を選ぶことができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4 小売業用カレンダー </p> </td> 
   <td colname="col2"> <p> 各月がその月の週数（1 月は 4 週など）で分けられています。National Retail Federation（全米小売業協会）は、この 4-5-4 カレンダーフォーマットを採用しています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムカレンダー </p> </td> 
   <td colname="col2"> <p> 各月の週数に基づいて 3 とおりの形式が用意されています。各月の週数は、その年の初日の選択により異なります。 </p> <p>1 年は 52 週です。それを 4 つの四半期に分けると、1 四半期あたり 13 週になります。しかし、1 四半期は 3 ヶ月です。13 は 3 で割り切れないので、常に一貫性が保たれるように、いずれか 1 つの月に余分な週を追加することになります。例えば、5-4-4 は四半期の 1 番目の月に余分の週があることを意味し、4-5-4 は四半期の 2 番目の月に余分の週があることを意味します。5-4-4 制のカレンダーでは、最後の四半期に 53 番目の週が追加されます。 </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>：1 月は 4 週、2 月は 5 週、3 月は 4 週などとなります。 </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>：例えば、1 月は 4 週、2 月は 4 週、3 月は 5 週になります。 </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>：例えば、1 月は 5 週、2 月は 5 週、3 月は 4 週になります。 </li> 
    </ul> <p>注意： このカレンダーオプションは、すべてのAdobe Analyticsツール(Analysis Workspace、Reports &amp; Analytics、Report BuilderおよびActivity Map)でサポートされています。 例外はData Warehouseで、カスタムカレンダーはサポートされません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

