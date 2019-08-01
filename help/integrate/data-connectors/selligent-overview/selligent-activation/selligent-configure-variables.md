---
description: この統合では、各レポートスイートの実装に対して2つのeVarを予約する必要があります。
seo-description: この統合では、各レポートスイートの実装に対して2つのeVarを予約する必要があります。
seo-title: 無制限のAnalytics変数の設定
solution: Analytics
title: 無制限のAnalytics変数の設定
uuid: 3b7b8b4b-7614-4439- bcb0- dbdec5304844
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configure Analytics Variables for Selligent{#configure-analytics-variables-for-selligent}

この統合では、各レポートスイートの実装に対して2つのeVarを予約する必要があります。

これらのeVarとは別に、Analyticsで表示したいデータに応じて、いくつかのイベントを予約できます。これらのeVarおよびイベントについて、以下のように説明します。

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数の種類 </th> 
   <th colname="col2" class="entry"> 変数名 </th> 
   <th colname="col3" class="entry"> 使用方法 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> メッセージID </td> 
   <td colname="col3"> 個々の電子メールメッセージキャンペーン識別を取り込むため。 </td> 
   <td colname="col4"> <p><b>ステータス</b>:有効にする </p> <p><b>配分</b>:最新 </p> <p><b>有効期限</b>:「ビジネス決定」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ev ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> 電子メールキャンペーンをクリックした顧客の匿名識別を取得する場合。 </td> 
   <td colname="col4"> <p><b>ステータス</b>:有効にする </p> <p><b>配分</b>:最新 </p> <p><b>有効期限</b>:「ビジネス決定」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 送信済み </td> 
   <td colname="col3"> 保証から送信される電子メールの数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 配信済み </td> 
   <td colname="col3"> 配信された電子メールの数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> 件数 </td> 
   <td colname="col3"> 表示された個別電子メールの数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Clicks </td> 
   <td colname="col3"> 電子メールがクリックされた回数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> バウンス </td> 
   <td colname="col3"> バウンスした電子メールの数を保存する場合。 </td> 
   <td colname="col4"> <p><b>タイプ</b>:数値 </p> <p><b>パーティシペーション</b>:有効にする </p> </td> 
  </tr> 
 </tbody> 
</table>

