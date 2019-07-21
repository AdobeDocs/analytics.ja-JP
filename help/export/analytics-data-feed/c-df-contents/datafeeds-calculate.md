---
description: データフィードを使用して一般的な指標を計算する方法について説明します。
keywords: データフィード;job;metrics;pre列;post列;ボット;date filtering;イベント文字列;common;公式
seo-description: データフィードを使用して一般的な指標を計算する方法について説明します。
seo-title: 指標の計算
solution: Analytics
title: 指標の計算
topic: Reports and Analytics
uuid: a45ea5bb-7c83-468f- b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 指標の計算

データフィードを使用して一般的な指標を計算する方法について説明します。

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## ボット {#section_06753B95800F47668AAF52E7227F27C8}

ボットは、レポートスイートに定義されている[ボットルール](https://marketing.adobe.com/resources/help/en_US/reference/?f=bot_rules)に従ってデータフィードから除外されます。

## 日付のフィルター {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

指定の期間内の行のみを含めるには、`date_time` フィールドをフィルター処理します。`date_time` フィールドは解読可能な状態であり、 `YYYY-MM-DD HH:MM:SS`レポートスイートのタイムゾーンに調整されます。For example, `date_time starts with "2013-12"` includes hits from December 2013.

## イベント文字列 {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. `post_event_list` は重複排除されており、同じ ID の重複イベントを排除するロジックが既に適用されているので、あらゆる処理はこちらの列に対して行うことを推奨します（「[イベントシリアル化](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_event_serialization)」を参照してください）。

イベント ID とイベント名のマッピングについては、データフィードで配信されるイベント参照を参照してください。

イベントの詳細については、「[events](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_events)」を参照してください。

## 一般的な指標の数式 {#section_E26A01C234484857BF8C74443222AE41}

一般的な指標の計算方法を以下の表に示します。

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指標 </th> 
   <th colname="col2" class="entry"> 計算方法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ページビュー </td> 
   <td colname="col2"> <p> ページビュー数は、<code>post_pagename</code> または <code>post_page_url</code> のどちらかに値がある場合にカウントすることで計算できます。 </p> 
    <p>同様のロジックでカスタムリンクの数もカウントできます。 </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code>post_page_event = 100</code> ではカスタムリンク数をカウントします。 </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code>post_page_event = 101</code> ではダウンロードリンク数をカウントします。 </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code>post_page_event = 102</code> では離脱リンク数をカウントします。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問回数 </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325"><code>exclude_hit &gt; 0</code> の行をすべて排除します。 </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5"><code>hit_source = 5,7,8,9</code> の行をすべて排除します。5、8、および 9 の行は、データソースを使用してアップロードされる概要行です。7 はトランザクション ID データソースアップロードを表し、これは訪問回数や訪問者数には含めません。詳しくは、 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> ヒットソース参照 </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D"><code>post_visid_high</code>、<code>post_visid_low</code>、<code>visit_num</code> および <code>visit_start_time_gmt</code>* を結合します。一意の結合数をカウントします。 </li> 
    </ol> <p>*まれに、インターネットの不整合、システムの不整合またはカスタム訪問者 ID の使用によって、異なる<code>訪問</code>の同じ訪問者 ID に対して <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=metrics_visit" format="http" scope="external">visit_num</a> 値が重複することがあります。問題の発生を避けるには、訪問をカウントする際に、<code>visit_start_time_gmt</code> も含めます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者数 </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D"><code>exclude_hit &gt; 0</code> の行をすべて排除します。 </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527"><code>hit_source = 5,7,8,9</code> の行をすべて排除します。5、8、および 9 の行は、データソースを使用してアップロードされる概要行です。7 はトランザクション ID データソースアップロードを表し、これは訪問回数や訪問者数には含めません。詳しくは、 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> ヒットソース参照 </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39"><code>post_visid_high</code> と <code>post_visid_low</code> を結合します。一意の結合数をカウントします。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベントインスタンス数 </td> 
   <td colname="col2"> <p>ヒットにイベントが設定されると、<code>post_event_list</code> にそのイベントが含まれます。<code>post_event_list</code> は重複排除されているので、イベントインスタンスの判別に推奨されます。 </p> <p>次に例を示します。 </p> 
    <code>post_ event_ list=1,200 </code>
  <p>これは、<code>purchase</code> と <code>event1</code> の 1 つのインスタンスを示します。 </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A"><code>exclude_hit &gt; 0</code> の行をすべて排除します。 </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB"><code>hit_source = 5,8,9</code> の行をすべて排除します。これらはデータソースを使用してアップロードされる概要行です。詳しくは、 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> ヒットソース参照 </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD"><code>post_event_list</code> 内にイベント参照の値が出現する回数をカウントします。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar インスタンス数 </td> 
   <td colname="col2"> <p>ヒットに eVar が設定されると、<code>event_list</code> にその eVar のインスタンスが含まれます。 </p> <p>次に例を示します。 </p> 
    <code>post_ event_ list&amp; amp;nbsp;= amp;nbsp;100,101,106 </code>
  <p>これは、<code>eVar1</code>、<code>eVar2</code>、および <code>eVar7</code> の 1 つのインスタンスを示します。つまり、ヒットにこれらの 3 つの eVar の値が設定されたことになります。 </p> <p>eVar のインスタンス数を計算するには、前述の「<i>イベントインスタンス数</i>」で説明したロジックと同じロジックを使用しますが、この場合は <code>post_event_list</code> 内に eVar 参照が出現する回数をカウントします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 滞在時間 </td> 
   <td colname="col2"> <p>滞在時間を計算するには、訪問別にヒットをグループ化してから、その訪問内のヒット数に従ってグループに順序を付けます。 </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F"><code>exclude_hit &gt; 0</code> の行をすべて排除します。 </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803"><code>visid_high</code>、<code>visid_low</code>、<code>visit_num</code> を連結して、1 回の訪問に対するヒットをグループ化します。 </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B"><code>visit_page_num</code> で各訪問に対するヒットに順序を付けます。 </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0"><a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-page-event.md#concept_A3AC076C3728445EB4CC572A6EDA5263" format="dita" scope="local"> page_ event </a>を使用して、ヒットのタイプをフィルターします。 </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">滞在時間の追跡に必要な値が設定されているヒットを探します。以下に例を示します。<code>hit1:post_ prop1= red hit2:post_ prop1= blue </code>
  </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">ヒット 1 の <code>post_cust_hit_time</code> をヒット 2 の <code>post_cust_hit_time</code> から引いて、これら 2 つのヒット間の秒数を決定します。結果は <code>post_prop1=red</code> の滞在時間になります。この結果が負数の場合は、ヒットを受信した順序が正しくないことを示しているため、計算を破棄する必要があります。 </li> 
    </ol> <p>このロジックを拡張して、他の値の滞在時間を計算できます。滞在時間を計算する場合、Analytics は <code>track</code> (<code>page_event=0</code>) または <code>trackLink</code> (<code>page_event=10|11|12</code>) の呼び出しで値が設定された時刻に基づいて、次のページビュー（<code>track</code> 呼び出し）の時刻までの滞在時間を計算します。 </p> <p>特定の期間の滞在時間をレポートする場合、Marketing Reports &amp; Analytics およびアドホック分析は、期間の開始日付または終了日付が月の境界に設定されている場合を除き、レポート期間を超えているヒットを評価して、レポート期間内の値に対する滞在時間を決定します。そのような計算は複雑であるため、滞在時間指標を正確に一致させることは難しい場合があります。データウェアハウスはレポート期間を超えているヒットを評価しません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 売上高、注文、数量 </td> 
   <td colname="col2"> <p>通貨換算は、レポートスイートの設定に従って <code>post_product_list</code> に適用されるので、この列の使用を推奨します。 </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16"><code>exclude_hit &gt; 0</code> の行をすべて排除します。 </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C"><code>hit_source = 5,8,9</code> の行をすべて排除します。5-9 は、データソースを使用してアップロードされる概要行を表します。詳しくは、 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> ヒットソース参照 </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733"><code>duplicate_purchase = 1</code> の行の購入データを無視します。このフラグは、購入が重複している（同じ <code>purchaseID</code> を持つヒットが既に記録されていた）ことを示します。 </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p><code>post_product_list</code> は <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_products" format="http" scope="external">s.products</a> と同じ構文を使用するので、この文字列を解析して指標を計算できます。次に例を示します。 </p> 
      <code>;;クロストレーナー;1;69.95，;スポーツソックス;10;29.99 </code>
  <p>この文字列を解析することによって、クロストレーナー 1 足 が $69.95 で購入されたことや、この購入の売上高合計が $99.94 だったことがわかります。 </p> </li> 
    </ol> <p>注意：Analytics では、製品の売上高を含む通貨イベントをイベント文字列で渡すことができるので、製品文字列に含まれない売上高の存在を考慮する必要があります。<i>s.events</i> の「<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_events" format="http" scope="external">数値／通貨イベント</a>」を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>
