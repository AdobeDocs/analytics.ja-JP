---
description: ほとんどの場合、Data Connectorウィザードによって生成される統合コードに変更を加える必要はありません。
seo-description: ほとんどの場合、Data Connectorウィザードによって生成される統合コードに変更を加える必要はありません。
seo-title: 統合コードの変更
title: 統合コードの変更
uuid: 3f49a29b- ad38-4967-894a- ef7ecf4d268f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 統合コードの変更{#modifying-the-integration-code}

ほとんどの場合、Data Connectorウィザードによって生成される統合コードに変更を加える必要はありません。

ただし、調整を行う必要がある場合は、コード設定の一部を以下に説明します。

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コード設定 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">Analytics収集サーバーへの起動前に、Adobe AnalyticsイメージリクエストがDemandbaseデータを待機する最大時間（ミリ秒）です。 <p>注意:この設定は、Integrateモジュールで実行される可能性のあるすべての統合に適用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._key </td> 
   <td colname="col2"> Demandbase APIキー。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ APIURL </td> 
   <td colname="col2"> Demandbase APIのURLテンプレート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._delim </td> 
   <td colname="col2"> Demandbaseディメンション値をAdobe Analyticsに送信する際に使用する区切り文字。この設定を変更すると、デフォルトの分類ルールが正しく機能しない場合があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ setTNT </td> 
   <td colname="col2">trueの場合、統合コードは、非表示のmboxを使用して、DemandbaseディメンションをプロファイルパラメーターとしてAdobe Targetに送信しようとします。 <p>注意:これにより、mbox. jsコードがページに存在する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ tntvarPrefix </td> 
   <td colname="col2"> この文字列は、Adobe Targetに送信する前に各Demandbaseディメンション名の先頭に付加されます。例えば、この設定に"db_"という値が設定されている場合、ディメンション"world"はAdobe Targetに"db_ world"として送信されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ dimensionArray </td> 
   <td colname="col2"> Adobe Analyticsに送信される標準的なDemandbaseディメンション。この設定を変更しないことをお勧めします。"max_ size"プロパティは、切り詰められる前にディメンションに許可されている文字数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ dimensionsArrayCustom </td> 
   <td colname="col2"> Adobe Analyticsに送信されるカスタムDemandbaseディメンション。"max_ size"プロパティは、切り詰められる前にディメンションに許可されている文字数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ cName </td> 
   <td colname="col2"> Demandbase API通信の状態を維持するために使用されるセッションcookieの名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ contextName </td> 
   <td colname="col2"> 標準ディメンションをAdobe Analyticsに送信するために使用されるcontextData変数の名前です。この設定を変更しないことをお勧めします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ contextNameSummary </td> 
   <td colname="col2"> カスタムディメンションをAdobe Analyticsに送信するために使用されるcontextData変数の名前です。この設定を変更しないことをお勧めします。 </td> 
  </tr> 
 </tbody> 
</table>

