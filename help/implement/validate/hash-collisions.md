---
title: ハッシュの競合
description: ハッシュの競合とは何かと、どのようにレポートで示されるかについて説明します。
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 100%

---

# ハッシュの競合

値が数値であっても、prop および eVar 値を文字列として扱います。これらの文字列が数百文字の長さになることもありますが、その他の場合は短くなります。スペースを節約し、パフォーマンスを向上させ、すべてを均一のサイズにするために、文字列は、処理で直接使用されません。代わりに、各値に 32 ビットまたは 64 ビットのハッシュが計算されます。すべてのレポートは、これらのハッシュ値に対して実行され、各ハッシュが元のテキストに置き換えられます。ハッシュを使用すると、Analytics レポートのパフォーマンスが大幅に向上します。

ほとんどのフィールドでは、文字列が最初にすべて小文字に変換されます（一意の値の数を削減）。値は、月ごとにハッシュ化されます（最初は毎月表示されます）。月ごとに、2 つの一意の変数値がハッシュ化されて同じ値になる可能性がわずかにあります。この概念は、*ハッシュの競合*&#x200B;として知られています。

ハッシュの競合は、次のようにしてレポートで示されます。

* 値のトレンドを確認していてある月にスパイクがある場合、その変数の別の値がハッシュ化されて、検討している値と同じ値になっている可能性があります。
* 特定の値のセグメントについても同じことが起こります。

## ハッシュの競合の例

ハッシュの競合の可能性は、ディメンションの一意の値の数と共に増加します。例えば、月の下旬に入ってきた値の 1 つは、月の初めの値と同じハッシュ値になる可能性があります。次の例で、いかにしてこれがセグメント結果を変更することにつながるかということを説明します。eVar62 が、2 月 18 日に &quot;値 100&quot; を受け取るとします。Analytics は、テーブルを次のように維持します。

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62 文字列値 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 値 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>値 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 値 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

eVar62=&quot;値 500&quot; である訪問者を探すセグメントを作成すると、Analytics は &quot;値 500&quot; がハッシュを含んでいるかどうかを判断します。&quot;値 500&quot; は存在しないので、Analytics は訪問数 0 を返します。次に、2 月 23 日に、eVar62 が &quot;値 500&quot; を受け取り、そのハッシュも 123 になります。テーブルは、次のようになります。

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62 文字列値 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 値 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>値 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 値 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>値 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

同じセグメントが再び実行されると、&quot;値 500&quot; のハッシュを探し、123 を見つけて、レポートはハッシュ 123 を含むすべての訪問数を返します。ここで、2 月 18 日に発生した訪問数が、この結果に含まれます。

この状況は、Analytics を使用する際に問題を生み出す可能性があります。アドビでは、引き続き、将来のハッシュの競合の可能性を低減する方法を調査します。変数間で一意の値を分散させる方法を見つけたり、処理ルールで不要な値を削除したり、変数ごとの値の数を減らしたりすることで、この状況を避けることができます。
