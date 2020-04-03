---
description: 指標の横にある歯車アイコンをクリックすると、指標タイプとアトリビューションモデルを指定できます。
title: 指標タイプとアトリビューション
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 指標タイプとアトリビューション

指標の横にある歯車アイコンをクリックすると、指標タイプとアトリビューションモデルを指定できます。

* [指標タイプ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [列のアトリビューションモデル](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [2018 年 7 月 19 日以降の線形配分の適用方法](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## 指標タイプ {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| 指標タイプ | 定義 |
|---|---|
| 標準 | これらの指標は、標準の [!DNL Analytics] レポートで使用される指標と同じです。1 つの標準指標で構成される数式は、その標準指標に対応する計算指標以外の指標と同じデータを表示します。標準指標は、個々の行項目に固有の計算指標を作成する場合に役立ちます。例えば、[購入回数] / [訪問回数]の場合、特定の行項目の購入回数を特定の行項目の訪問回数で割ります。 |
| 合計 | 各行項目のレポート期間の合計を使用します。1 つの合計指標で構成される数式は、各行項目で同じ合計数を表示します。合計指標は、サイト合計データと比較する計算指標を作成する場合に役立ちます。例えば、[購入回数] / [合計訪問回数]は、特定の行項目への訪問回数だけでなく、サイトへのすべての訪問回数に対する購入回数の割合を示します。 |

## 列のアトリビューションモデル {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>2018 年 7 月に、計算指標における配分モデルの評価方法を変える [Attribution IQ](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/attribution.html) が [!DNL Analytics] に導入されました。この変更の一環として、デフォルト以外の配分モデルを使用する計算指標は、新しく改善されたアトリビューションモデルに移行されました。
>
>* デフォルト以外のアトリビューションモデルの完全なリストとサポートされるルックバックウィンドウについては、[Attribution IQ](https://marketing.adobe.com/resources/help/ja_JP/analytics/analysis-workspace/attribution.html) のドキュメントを参照してください。
>* 「マーケティングチャネルラストタッチ」と「マーケティングチャネルファーストタッチ」配分モデルはそれぞれ、新しい「ラストタッチ」と「ファーストタッチ」アトリビューションモデルに移行されます（注意：「マーケティングチャネル」は廃止されません。計算指標で表示される 2 つの配分モデルのみが廃止されます）。
>* さらに、線形配分の計算方法が修正されます。顧客が線形配分モデルで計算指標を使用する場合、修正された新しいアトリビューションモデルを反映してレポートが若干変わる可能性があります。この計算指標の変更は、Analysis Workspace[!UICONTROL 、Reports &amp; Analytics]、レポート API、Report Builder、および Ad Hoc Analysis に反映されます。詳しくは、[2018 年 7 月 19 日以降の線形配分の適用方法](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)を参照してください。
>



## 2018 年 7 月 19 日以降の線形配分の適用方法{#section_EDBB2E14A6C248C5A79C0913C02D7CA1}

2018 年 7 月に、Adobe での計算指標に関する線形配分のレポート方法が変更されました。この変更は、Analysis Workspace、Ad Hoc Analysis、[!UICONTROL Reports &amp; Analytics]、Report Builder、Activity Map およびレポート API に影響します。主に影響が及ぶのは、eVar と永続性のあるその他のディメンションです。なお、これらの変更が適用されるのは計算指標のみで、線形配分を使用する他のレポート（[!UICONTROL Reports &amp; Analytics] のページレポートなど）には影響しません。線形配分を使用する他のレポートについては、引き続き、既存の線形配分手法が利用されます。

次の例で、線形配分での計算指標のレポート時における変更内容について示します。

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> ヒット 1 </th> 
   <th colname="col3" class="entry"> ヒット 2 </th> 
   <th colname="col4" class="entry"> ヒット 3 </th> 
   <th colname="col5" class="entry"> ヒット 4 </th> 
   <th colname="col6" class="entry"> ヒット 5 </th> 
   <th colname="col7" class="entry"> ヒット 6 </th> 
   <th colname="col8" class="entry"> ヒット 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>送信データ </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ラストタッチ eVar </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> PROMO B </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファーストタッチ eVar </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> PROMO A </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO A </td> 
   <td colname="col6"> PROMO A </td> 
   <td colname="col7"> PROMO A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop 例 </p> </td> 
   <td colname="col2"> PROMO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMO A </td> 
   <td colname="col5"> PROMO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

この例では、ヒット 7 で $10 の購入が行われる前に、値 A、B、C がヒット 1、3、4、6 の変数に送信されました。2 番目の行では、ラストタッチでの訪問がベースとなり、ヒット全体に値が持続されています。3 番目の行では、ファーストタッチでの訪問が持続されていることがわかります。最後の行には、持続性のない prop に記録されるデータの内容が示されています。

**2018 年 7 月より前の線形配分の適用方法の概要**

2018 年 7 月 19 日以前は、線形アトリビューションは、ファーストタッチまたはラストタッチの持続性が生じた後に計算されました。つまり、上のラストタッチの eVar の場合、$10 は、A = 10 *（3/6） = $5、B = 10 *（2/6） = $3.33、C = 10 *（1/6） = $1.67 のように配分されていました。

上のファーストタッチの eVar の場合であれば、$10 はすべて A に与えられていました。prop の場合は、A = 10 *（2/4） = $5、B = 10 *（1/4） = $2.50、C = 10 *（1/4） = $2.50 のようになりました。以前の線形配分の適用方法をまとめると、次のようになります。

| 値 | 現在のラストタッチの eVar | 現在のファーストタッチの eVar | 現在の Prop |
|---|---|---|---|
| PROMO A | $5.00 | $10.00 | $5.00 |
| PROMO B | $3.33 | $0 | $2.50 |
| PROMO C | $1.67 | $0 | $2.50 |
| 合計 | $10.00 | $10.00 | $10.00 |

**2018 年 7 月 19 日以降の線形配分の適用方法の概要**

7 月 19 日以降、計算指標でのこの動作は修正されました。ラストタッチまたはファーストタッチに基づいた持続的な値を使用する代わりに、[!DNL Analytics] では渡された値のみを使用します（上の表の最初の列）。そうすることで、ディメンションの配分設定が線形配分の計算内容に影響しなくなります（つまり、prop と eVar が同じように扱われます）。また、ファーストタッチまたはラストタッチの持続的な値ではなく、当初に渡された値が結果に反映されます。したがって、3 つのケースすべてで次のようになります：A = 10 * (2/4) = $5、B = 10 * (1/4) = $2.50、C = 10 * (1/4) = $2.50

| 値 | 新しいラストタッチの eVar | 新しいファーストタッチの eVar | 新しい Prop |
|---|---|---|---|
| PROMO A | $5.00 | $5.00 | $5.00 |
| PROMO B | $2.50 | $2.50 | $2.50 |
| PROMO C | $2.50 | $2.50 | $2.50 |
| 合計 | $10.00 | $10.00 | $10.00 |

<!-- 

<p>Additionally, as part of this change, [!DNL Analytics] is <b>changing how multiple sequential successes</b> are treated. In the following example, 7 hits occurred in the same visit with two orders, one $10 order on hit 4, and one $5 order on hit 7: </p> 
<table id="table_4647AA466D1447F6961DDC10468FCCE1"> 
 <tgroup cols="8">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="1.04*" />
  <colspec colnum="3" colname="col3" colwidth="1.02*" />
  <colspec colnum="4" colname="col4" colwidth="1.02*" />
  <colspec colnum="5" colname="col5" colwidth="1.03*" />
  <colspec colnum="6" colname="col6" colwidth="1.02*" />
  <colspec colnum="7" colname="col7" colwidth="1.02*" />
  <colspec colnum="8" colname="col8" colwidth="1.03*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> </th> 
    <th colname="col2" class="entry"> Hit 1 </th> 
    <th colname="col3" class="entry"> Hit 2 </th> 
    <th colname="col4" class="entry"> Hit 3 </th> 
    <th colname="col5" class="entry"> Hit 4 </th> 
    <th colname="col6" class="entry"> Hit 5 </th> 
    <th colname="col7" class="entry"> Hit 6 </th> 
    <th colname="col8" class="entry"> Hit 7 </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Data Sent In </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Last Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO B </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>First Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO A </td> 
    <td colname="col7"> PROMO A </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Example prop </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p>Currently (<b>prior to July 19, 2018</b>), linear attribution would carry forward past the initial conversion and persist into the second conversion </p> 
<ul id="ul_FD09813B59F04FF2A96A70BBE0A8F349"> 
 <li id="li_2EC965DDAE334C1795530F7C6F1674C5">In our first-touch eVar example, the total revenue for each promotion would be calculated using the promos prior to conversion on hit 4 for revenue on hit 4, but all promos for the conversion on hit 7. </li> 
 <li id="li_687C03C4B0A941AA800084F324A95FD6">In our last-touch eVar example, this would be: A = (2/3) * 10 + (2/5) * 5 = $8.66, B = (1/3) * 10 + (2/5) * 5 = $5.33, C = (1/5) * 5 = $1.00. In our FT eVar example: A = (3/3) * 10 + (5/5) * 5 = $15.00, and for the prop: A = (1/2) * 10 + (1/3) * 5 = $6.66, B = (1/2) * 10 + (1/3) * 5 = $6.66, and C = (1/3) * 5 = $1.66. </li> 
</ul> 
<p>Resulting in a distribution as follows: </p> 
<table id="table_6A066E602BF641B0BD4B175EE9753C6E"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> Current Last Touch eVar </th> 
    <th colname="col3" class="entry"> Current First Touch eVar </th> 
    <th colname="col4" class="entry"> Current Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $8.66 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.33 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $1.00 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $1.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p><b>After July 19, 2018</b>, [!DNL Analytics] will treat each sequence of conversions independently, meaning linear attribution will no longer carry forward from one conversion to another. In the previous example, attribution will always be treated the same way (regardless of the eVar allocation settings as stated above) and will be calculated as follows: A = (1/2) * 10 = $5, B = (1/2) * 10 = $5, and C = (1/1) * 5 = $5. To summarize: </p> 
<table id="table_2D39CCD158BF488EA404324DF50B9579"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> New Last Touch eVar </th> 
    <th colname="col3" class="entry"> New First Touch eVar </th> 
    <th colname="col4" class="entry"> New Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

