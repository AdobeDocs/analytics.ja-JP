---
description: レポートビルダーでは、Analytics カスタムカレンダーを使用します。 カレンダーを使用して、週と年の最初の日を定義したり、別の小売カレンダースタイルを使用したりできます。 カレンダー形式は、売上比較や予測標準化、給与計算コスト分析、実店舗在庫数規制など、さまざまな目的で使用されます。
title: カスタムカレンダー
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
TQID: https://experienceleague.adobe.com/At3YiOPV0jx5WXwe-VvA05n3yIEmiAJIRzoOoeISeA4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 15%

---

# カスタムカレンダー

{{legacy-arb}}

レポートビルダーでは、Analytics カスタムカレンダーを使用します。 カレンダーを使用して、週と年の最初の日を定義したり、別の小売カレンダースタイルを使用したりできます。 カレンダー形式は、売上比較や予測標準化、給与計算コスト分析、実店舗在庫数規制など、さまざまな目的で使用されます。

各カレンダー形式について以下に説明します。

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> カレンダー </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>グレゴリオ暦 </p> </td> 
   <td colname="col2"> <p> 従来のカレンダー形式（1月から12月まで、30日または31日と各月の週数を指定）を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>修正グレゴリオ暦カレンダー </p> </td> 
   <td colname="col2"> <p> 従来のグレゴリオ暦を使用しますが、年の最初の月と週の最初の日を選択できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4小売カレンダー </p> </td> 
   <td colname="col2"> <p> 毎月の週数を計算します。 つまり、1月には4週間などです。 全米小売業協会は、4-5-4 カレンダー形式を使用しています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムカレンダー </p> </td> 
   <td colname="col2"> <p> 毎月の週数に基づいて3つの形式を提供します。 各月の週数は、その年の初日の選択によって異なります。 </p> <p>1年は52週間です。 それを4四半期に分けて、四半期ごとに13週間とします。 しかし、四半期には3 ヶ月があります。 13 は 3 で割り切れないので、常に一貫性が保たれるように、いずれか 1 つの月に余分な週を追加することになります。 5/4/4は、四半期の第1月に追加の週があることを意味します。 4/5/4は、2番目の月に余分な週が含まれているという意味です。5-4-4 カレンダーでは、53週目が年の最後の四半期に追加されます。 </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>:1月には4週間、2月には5週間、3月には4週間など。 </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: 1月は4週間、2月は4週間、3月は5週間など。 </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>: 1月は5週間、2月は5週間、3月は4週間など。 </li> 
    </ul> <p>注意：このカレンダーオプションは、Analysis Workspace、Report Builder、Activity MapのすべてのAdobe Analytics ツールでサポートされています。 例外は Data Warehouse で、これはカスタムカレンダーをサポートしていません。 </p> </td> 
  </tr> 
 </tbody> 
</table>
