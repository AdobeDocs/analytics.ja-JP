---
description: 処理ルールを使用して（特記がない限り）読み取りおよび書き込みが可能なディメンションです。
subtopic: Processing rules
title: 処理ルールで使用可能なディメンション
topic: Admin tools
uuid: ba73ab59-a8cf-491c-8757-5fb03d6b0745
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 86%

---


# 処理ルールで使用可能なディメンション

処理ルールを使用して（特記がない限り）読み取りおよび書き込みが可能なディメンションです。

## カスタム値とコンテキストデータ  {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 値 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>カスタム値 </p> </td> 
   <td colname="col2"> <p>処理ルールのアクションに直接入力されるカスタムテキストまたは値。これらの値は、後続の条件およびルールでも使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>連結値 </p> </td> 
   <td colname="col2"> <p>2 つの値を組み合わせて作成される値。例えば、カテゴリとページ名を組み合わせて、サブカテゴリーを作成できます。これらの値は、後続の条件およびルールでも使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>変更した値 </p> </td> 
   <td colname="col2"> <p>処理ルールを使用して変数値を変更すると、変更した値が後続の条件とルールで使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンテキストデータ変数 </p> </td> 
   <td colname="col2"> <p>ヒットで送信される名前付き変数。 </p> <p>注意：コンテキストデータ変数に含まれるすべてのデータは、レポート内で表示するためにレポート変数にコピーする必要があります。コンテキストデータ変数は、クリックストリームデータフィードなどのレポートインターフェイスで表示できません。 </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md">コンテキストデータ変数の eVar へのコピー </a> </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md">コンテキストデータ変数を使用したイベントの設定 </a> </p> <p> <a href="/help/implement/vars/page-vars/contextdata.md">コンテキストデータ変数</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## トラフィック変数 {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1 ～ 75 </p> </td> 
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>階層 1 ～ 5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サイトセクション </p> </td> 
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバー </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## ヒット属性 {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 属性 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>レポートスイート ID（読み取り専用） </p> </td> 
   <td colname="col2"> <p>処理ルールを実行するレポートスイート。AppMeasurement で指定した元のレポートスイートではない場合があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページ名 </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>注意： リンクトラッキングの呼び出しは、処理ルールに到達する前に<code>pageName</code>変数を取り除きます。 処理ルールを使用してページ名の値を再挿入すると、そのヒットは、リンクトラッキング呼び出しではなく、ページ表示と見なされます。 ページ名を変更する前に、ページ名が既に設定されていることを確認することをAdobeが推奨します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページ URL </p> </td> 
   <td colname="col2"> <code> s.pageURL</code>。<code> s.pageURL</code> が指定されていない場合は現在のページ URL。 <p>注意： リンクトラッキングの呼び出しは、処理ルールに到達する前に<code>pageURL</code>変数を取り除きます。 処理ルールを使用してページURL値を再挿入する場合、ヒットはリンクトラッキング呼び出しではなくページ表示と見なされます。 ページURLを変更する前に、ページURLが既に設定されていることをAdobeが確認することをお勧めします。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>クエリー文字列パラメーター </p> </td> 
   <td colname="col2"> <p>現在の URL で指定したクエリー文字列パラメーターの値。パラメーターが存在しない場合は null。URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b> の場合、クエリー文字列パラメーター <span class="syntax codeph">cid</span> の値は <b>ad1</b> であり、クエリー文字列パラメーター <span class="syntax codeph">node</span> の値は <b>4</b> です。 </p> <p>JavaScript s_code AppMeasurement H.25.2 以前を実行している場合、ページ URL は 255 字で切り捨てられます。JavaScript s_code AppMeasurement H.25.3（2013 年 1 月のリリース）以降では、処理ルールに完全修飾 URL が提供されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページパス </p> </td> 
   <td colname="col2"> <p>ページ URL のパス。URL <b>https://www.example.com/news/a.html?cid=ad1</b> のパスは <span class="syntax codeph">news/a.html</span> です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページドメイン </p> </td> 
   <td colname="col2"> <p>URL に指定されている完全なホスト名。https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページルートドメイン </p> </td> 
   <td colname="col2"> <p>ページのホスト名の最後の 2 つのセクション。https://en.main.example。<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ページクエリー文字列 </p> </td> 
   <td colname="col2"> <p>URL の完全なクエリー文字列。https://en.main.example.co.uk/index.jsp? <span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リファラー*（読み取り専用） </p> </td> 
   <td colname="col2"> <p>HTTP リファラー。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参照クエリー文字列パラメーター（読み取り専用） </p> </td> 
   <td colname="col2"> <p>参照 URL で指定したクエリー文字列パラメーターの値。パラメーターが存在しない場合は null。URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b> の場合、クエリー文字列パラメーター <span class="syntax codeph">cid</span> の値は <b>ad1</b> であり、クエリー文字列パラメーター <span class="syntax codeph">node</span> の値は <b>4</b> です。 </p> <p>JavaScript s_code AppMeasurement H.25.2 以前を実行している場合、ページ URL は 255 字で切り捨てられます。JavaScript s_code AppMeasurement H.25.3（2013 年 1 月のリリース）以降では、処理ルールに完全修飾 URL が提供されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参照ドメイン（読み取り専用） </p> </td> 
   <td colname="col2"> <p>リファラーのフルホスト名。https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参照ルートドメイン（読み取り専用） </p> </td> 
   <td colname="col2"> <p>リファラーのホスト名の最後の 2 つのセクション。https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参照クエリー文字列（読み取り専用） </p> </td> 
   <td colname="col2"> <p>参照 URL に含まれるクエリー文字列パラメーター。https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP アドレス（読み取り専用） </p> </td> 
   <td colname="col2"> <p>ブラウザーから報告される IP アドレス。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザーエージェント（読み取り専用） </p> </td> 
   <td colname="col2"> <p>ブラウザーから報告されるユーザーエージェント。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AppMeasurement コードバージョン（読み取り専用） </p> </td> 
   <td colname="col2"> <p>要求を行うために使用される appMeasurement ライブラリのバージョン。イメージビーコンを使用する場合、この値をカスタム値に設定できます。この値は、処理ルールによって読み取られます。この値は、URL の次の位置に示されます。 </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## コンバージョン変数 {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> - <code> evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>キャンペーントラッキングコード </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>通貨コード </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リスト変数 1 ～ 3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> -  <code> s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>購入 ID </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>トランザクション ID </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪問者の州 </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪問者の郵便番号 </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 成功イベント {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

処理ルールでイベントを設定できますが、条件としてイベントを読み込むことはできません。

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> イベント </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>イベント1 ～ 1000 </p> <p>（SiteCatalyst 15 のお客様の場合、イベント 1 ～ 100） </p> </td> 
   <td colname="col2"> <p> <code> event1</code> -  <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchase、scView、scAdd およびその他の買い物かごイベント </p> </td> 
   <td colname="col2"> <p>定義済みのイベント。 </p> </td> 
  </tr> 
 </tbody> 
</table>

