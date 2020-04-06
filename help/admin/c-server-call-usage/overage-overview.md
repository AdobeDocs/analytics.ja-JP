---
description: 'null'
title: サーバーコールの使用状況の概要
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# サーバーコールの使用状況の概要

## サーバーコールの使用状況を監視してアラートを表示する理由 {#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics Server Call Usageは、ブラウザーとモバイルサーバーの両方の呼び出しの使用データに対する透明性の要求に対処します。 次の項目にアクセスできます。

* サーバーコールの使用ダッシュボード。サーバーコールの消費データを追跡し、契約上の制限と比較します。(**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* A Server Call Usage alert type in the Alert Builder that lets you set up alerts to prevent overages (**[!UICONTROL Analytics > Components >Alerts]**)

サーバーコールの使用の主な利点は次のとおりです。

* **契約上の** 、サーバーコールの使用制限に対するモバイルの使用を含む、サーバーコールの使用状況と取り組みデータの可視化。
* **過剰** （超過）が発生するリスクや発生を通知し、過大な被害が発生する可能性に対する準備・対応を行うよう警告する。

Previously, while you could access monthly server call consumption data under  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]** , this data was only updated 6 days after billing had closed for that month. さらに、このデータには、モバイルでの使用が含まれていませんでした。この機能は、/の現在のレポート **[!UICONTROL Billing Information]** も置き換 **[!UICONTROL Analytics]** えられま **[!UICONTROL Reports]** す。

## 前提条件 {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **権限：**&#x200B;サーバーコール使用状況ダッシュボード、アラートビルダー、アラートマネージャーにアクセスするには、Adobe Analytics 管理者である必要があります。
* **権限：** 管理者は、管理者以外のユーザーにアクセス権を付与できます。権限が呼び出されま **[!UICONTROL Server Call Usage]**&#x200B;す。 詳しくは、[サーバーコールの使用状況に関する権限](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369)を参照してください。

## 重要な用語 {#section_CBA348A039F34563B097CD8890AB358D}

サーバーコールの使用に関する基本的な用語の簡単な入門書を示します。

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用語 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>サーバーコール </p> </td> 
   <td colname="col2"> <p>「ヒット」または「イメージリクエスト」とも呼ばれるサーバーコールは、処理のためにアドビのサーバーにデータが送信されるインスタンスです。 最も一般的なタイプのサーバー呼び出しは、ページ表示です。 ページビューでは、訪問者が Web サイトのページを閲覧し、アドビ向けのサーバーコールが生成されます。アドビでは、情報が収集されて処理され、レポート指標に含まれます。 </p> <p>出口リンクやファイルのダウンロードなど他のタイプのサーバーコールでは、データが処理のためにアドビに送信されますが、新規ページビューとしては記録されません。「除外」ページ表示（設定したIPアドレスの範囲などによって、レポートから除外）でも、アドビが受信して処理するので、サーバーコールですが、レポートには表示されません。 </p> <p><b>Primary Server Call</b>:Webサイトのデータ挿入ブラウザーまたは訪問者挿入APIから直接受け取ったリクエスト。 プライマリヒット(ページ表示)、プライマリカスタムイベント、プライマリダウンロードイベント、プライマリ終了イベントが含まれます。 </p> <p><b>Secondary Server Call</b>:複数スイートタグで作成された、またはVISTAルールでコピー/移動されたプライマリサーバーコールのコピー。 セカンダリサーバ呼び出しがVISTAルールによって別のレポートスイートに（コピーではなく）移動された場合、セカンダリ呼び出しの累積数はプライマリサーバ呼び出しから引かれます。 </p> <p><b>モバイルプライマリサーバーコール </b> </p> <p>いずれかの Mobile SDK から直接受け取ったリクエスト。これには、trackAction、trackState、trackApp Crashes、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrease が含まれます。</p> <p><b>モバイルセカンダリサーバーコール</b> </p> <p>複数のスイートのタグによって作成されたか、Vista ルールによってコピー／移動されたプライマリサーバーコールのコピーです。セカンダリサーバ呼び出しがVISTAルールによって別のレポートスイートに（コピーではなく）移動された場合、セカンダリ呼び出しの累積数はプライマリサーバ呼び出しから引かれます。 </p> <p>注意：契約上、モバイルサーバーコール（プライマリまたはセカンダリ）しか使用できない場合、Web 限定の使用量もモバイル限定の使用量もモバイル限定コミットメントの分としてカウントされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>請求会社（請求 ID） </p> </td> 
   <td colname="col2"> <p>サーバーコールに対して請求される法人。 例えば、adobe.comのように指定します。 各請求会社には請求 ID があり、これを使用して請求先顧客を一意に識別します。請求 ID は複数の Experience Cloud 組織に関連付けることができ、組織と請求 ID の間には必ずしも 1 対 1 の関係はありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ログイン会社 </p> </td> 
   <td colname="col2"> <p>1 つの請求会社が<a href="https://helpx.adobe.com/jp/analytics/kb/multiple-login-companies.html">複数のログイン会社</a>を持つことができます。ログイン会社は、組織で使用されるレポートスイートの集まりです。 組織によっては、組織の異なる部分に適用される複数のログイン会社を持つ場合があります。 これは特に、様々な事業単位を扱う大規模な組織で、多くのレポートスイートが会社内の他のユーザーには適用されない場合に便利です。 </p> <p>多くの場合、これらは地域の会社会社です。 次の例は、ログイン会社と関連するレポートスイートを示しています。 </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide:RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us:RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in:RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de:RS4 </li> 
    </ul> <p>注意：請求会社内の<u>全</u>レポートスイートのサーバーコール使用状況データは、適切な<a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">権限</a>を持つすべてのユーザーから参照できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud組織 </p> </td> 
   <td colname="col2"> <p> 組織は、管理者がグループおよびユーザーの設定や、Experience Cloud でのシングルサインオンの制御をおこなえるエンティティです。組織は、すべての Experience Cloud 製品およびソリューションをまたいだログイン会社のように機能します。 </p> <p>ほとんどの場合、組織は会社名です。 ただし、1つの会社には多くの組織が含まれます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバーコールのコミットメント </p> </td> 
   <td colname="col2"> <p>会社がアドビとの契約に署名すると、アドビの販売チームは、お客様、お客様、タイプ（プライマリ、セカンダリ、モバイルプライマリ、モバイルセカンダリ）、契約期間中に発生する予定のサーバー呼び出しのおよそ数を特定します。 これは、サーバーコールの合計の取り組みです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用期間 </p> </td> 
   <td colname="col2"> <p>サーバーコールの使用状況の監視の目的では、このサーバーコールの総使用期間が3か月などの短い期間に分類され、前年比の比較が容易になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>契約期間 </p> </td> 
   <td colname="col2"> <p>契約期間は複数年間に及ぶ場合があります。 例えば、お客様の会社が、3年間の契約期間に600万件のサーバーコールを契約しているとします。 サーバーコールの使用状況を監視するために、この 3 年間をより短い使用期間に分けて、前年との比較を実行しやすくすることができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## サーバーコールの使用状況に関する権限 {#section_FCC58EB635954A32990D4E67B52B4369}

サーバーコールの使用権限は、Analytics管理者に自動的に付与されます。 この機能を使用すると、ユーザーが表示をダッシュボードし、サーバーコールの警告を作成できます。 管理者は、管理者以外のユーザーにこの権限を付与できます。

>[!NOTE]会社は、サーバーコールの使用状況にアクセスできるログイン会社を選ぶことができます。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 権限名 </th> 
   <th colname="col3" class="entry"> Adobe Analyticsにログインしている場合は権限を付与（従来のログイン） </th> 
   <th colname="col4" class="entry"> Adobe Experience Cloudにログインしている場合は権限を付与 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>サーバーコールの使用状況 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">sc.omniture.comからAnalyticsにログインします。 </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A"><span class="ignoretag"><span class="uicontrol">管理者</span>／<span class="uicontrol">ユーザー管理</span>／<span class="uicontrol">グループ</span>／<span class="uicontrol">全レポートアクセスの編集</span>／<span class="uicontrol">Analytics ツール</span>／<span class="uicontrol">カスタマイズ</span>／<span class="uicontrol">サーバーコールの使用状況</span></span>を選択します。 </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">login.experiencecloud.adobe.com にログインします。</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">「<span class="uicontrol">Analytics</span>」をクリックします。 </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF"><span class="ignoretag"><span class="uicontrol">製品</span>／<span class="uicontrol">製品プロファイル</span>／<span class="uicontrol">権限設定</span>／<span class="uicontrol">Analytics ツール</span>／<span class="uicontrol">サーバーコールの使用状況</span></span>を選択します。 </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

