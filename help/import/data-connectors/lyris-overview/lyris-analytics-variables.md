---
description: 各レポートスイートの実装に予約されるeVarおよびイベントについて説明します。
seo-description: 各レポートスイートの実装に予約されるeVarおよびイベントについて説明します。
seo-title: Livris用のAdobe Analytics変数の設定
solution: Analytics
title: Livris用のAdobe Analytics変数の設定
uuid: 12e150c4-052a-481c-8c27- ef45ee801977
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Livris用のAdobe Analytics変数の設定{#configure-adobe-analytics-variables-for-lyris}

各レポートスイートの実装に予約されるeVarおよびイベントについて説明します。

この統合では、各レポートスイートの実装に対して少なくとも2つのeVarを予約する必要があります。これらのeVarとは別に、Analyticsに表示するLyrisデータに応じて、いくつかのイベントを予約できます。これらのeVarおよびイベントについて、以下の表で説明します。

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数の種類 </th> 
   <th colname="col2" class="entry"> 変数名 </th> 
   <th colname="col3" class="entry"> 変数の使用方法 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> メッセージID </td> 
   <td colname="col3"> 個々の電子メールメッセージキャンペーンの識別を取り込むには </td> 
   <td colname="col4"> <p>ステータス:有効にする </p> <p>配分:最新 </p> <p>有効期限:「ビジネス決定」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> 電子メールキャンペーンをクリックした顧客の匿名識別を取り込むには </td> 
   <td colname="col4"> <p>ステータス:有効にする </p> <p>配分:最新 </p> <p>有効期限:「ビジネス決定」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris-送信済み電子メール </td> 
   <td colname="col3"> 保存しない。Lyrisから送信された電子メール </td> 
   <td colname="col4">タイプ:数値 <p>パーティシペーション:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris-開封済み電子メール </td> 
   <td colname="col3"> 保存しない。開封された電子メールの </td> 
   <td colname="col4">タイプ:数値 <p>パーティシペーション:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris-開封済み電子メール </td> 
   <td colname="col3"> 保存しない。開封された一意の電子メールの </td> 
   <td colname="col4">タイプ:数値 <p>パーティシペーション:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris-電子メールクリックスルー </td> 
   <td colname="col3"> 保存しない。電子メールがクリックされた回数 </td> 
   <td colname="col4">タイプ:数値 <p>パーティシペーション:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris-電子メールバウンス </td> 
   <td colname="col3"> 「いいえ」を保存する場合。バウンスした電子メールの </td> 
   <td colname="col4">タイプ:数値 <p>パーティシペーション:有効にする </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント </td> 
   <td colname="col2"> Lyris-電子メールの購読解除 </td> 
   <td colname="col3"> 「いいえ」を保存する場合。無効だった電子メールの購読 </td> 
   <td colname="col4">タイプ:数値 <p>パーティシペーション:有効にする </p> </td> 
  </tr> 
 </tbody> 
</table>

