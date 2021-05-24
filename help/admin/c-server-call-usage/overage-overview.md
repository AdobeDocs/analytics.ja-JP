---
description: Adobe Analytics サーバーコールの使用機能の概要です。
title: サーバーコールの使用状況の概要
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 98%

---

# サーバーコールの使用状況の概要

## サーバーコールの使用状況を監視してアラートを表示する理由  {#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics のサーバーコール使用状況の機能は、ブラウザーとモバイルからのサーバーコールの使用状況に関するデータを透過的に把握したいというお客様の要望に応えるものです。これを利用すると、以下にアクセスできます。

* サーバーコールの使用に関するデータを追跡して契約上の上限と比較するサーバーコール使用状況ダッシュボード。（**[!UICONTROL Analytics／管理者／サーバーコールの使用状況]**）
* アラートビルダーのサーバーコールの使用状況アラートタイプを使用してアラートを設定することで、超過使用を防ぐことができます（**[!UICONTROL Analytics／コンポーネント/アラート]**）。

サーバーコールの使用状況の主な利点は以下のとおりです。

* **可視性**：サーバーコールの使用およびコミットメントに関するデータ（モバイルでの使用量と契約上のサーバーコール使用量の上限の比較など）を正確に把握できます。
* **アラート**：超過使用が発生する危険性をユーザーに知らせ、超過分の費用負担の可能性に備えたり対処したりできるようにするためのアラートが表示されます。

これまでは、**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL 課金]**&#x200B;で毎月のサーバーコール使用データにアクセスできましたが、このデータはその月の請求が締め切られてから 6 日後にしか更新されませんでした。さらに、このデータには、モバイルでの使用が含まれていませんでした。この機能は、**[!UICONTROL Analytics]**／**[!UICONTROL レポート]**&#x200B;でアクセスできる現在の&#x200B;**[!UICONTROL 課金情報]**&#x200B;レポートも置き換えます。

## 前提条件 {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **権限：**&#x200B;サーバーコール使用状況ダッシュボード、アラートビルダー、アラートマネージャーにアクセスするには、Adobe Analytics 管理者である必要があります。
* **権限：**&#x200B;管理者は管理者以外のユーザーにアクセス権を付与できます。この権限は&#x200B;**[!UICONTROL サーバーコールの使用状況]**&#x200B;と呼ばれます。詳しくは、[サーバーコールの使用状況に関する権限](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369)を参照してください。

## 重要な用語 {#section_CBA348A039F34563B097CD8890AB358D}

サーバーコールの使用状況に不可欠な用語を簡単に解説します。

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
   <td colname="col2"> <p>「ヒット」または「イメージリクエスト」とも呼ばれます。処理するデータをアドビのサーバーに送信するインスタンスです。サーバーコールの最も一般的なタイプは、ページビューです。ページビューでは、訪問者が Web サイトのページを閲覧し、アドビ向けのサーバーコールが生成されます。アドビでは、情報が収集されて処理され、レポート指標に含まれます。 </p> <p>出口リンクやファイルのダウンロードなど他のタイプのサーバーコールでは、データが処理のためにアドビに送信されますが、新規ページビューとしては記録されません。「除外」ページビュー（設定する IP アドレスの範囲などによって、レポートから除外）でさえも、アドビが受信して処理するので、サーバーコールですが、レポートに表示されることはありません。 </p> <p><b>プライマリサーバーコール</b>：Web サイト訪問者のブラウザーまたは Data Insertion API から直接受け取った要求です。プライマリヒット（ページビュー）、プライマリカスタムイベント、プライマリダウンロードイベントおよびプライマリ終了イベントが含まれます。 </p> <p><b>セカンダリサーバーコール</b>：複数のスイートのタグによって作成されたか、VISTA ルールによってコピー／移動されたプライマリサーバーコールのコピーです。VISTA ルールによってセカンダリサーバーコールが別のレポートスイートに（コピーではなく）移動された場合は、セカンダリコールの合計数がプライマリサーバーコール数から差し引かれます。 </p> <p><b>モバイルプライマリサーバーコール</b> </p> <p>いずれかの Mobile SDK から直接受け取ったリクエスト。これには、trackAction、trackState、trackApp Crashes、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrease が含まれます。</p> <p><b>モバイルセカンダリサーバーコール</b> </p> <p>複数のスイートのタグによって作成されたか、Vista ルールによってコピー／移動されたプライマリサーバーコールのコピーです。VISTA ルールによってセカンダリサーバーコールが別のレポートスイートに（コピーではなく）移動された場合は、セカンダリコールの合計数がプライマリサーバーコール数から差し引かれます。 </p> <p>注意：契約上、モバイルサーバーコール（プライマリまたはセカンダリ）しか使用できない場合、Web 限定の使用量もモバイル限定の使用量もモバイル限定コミットメントの分としてカウントされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>請求会社（請求 ID） </p> </td> 
   <td colname="col2"> <p>サーバーコールの費用を請求される法人。例えば、adobe.com などです。各請求会社には請求 ID があり、これを使用して請求先顧客を一意に識別します。請求 ID は複数の Experience Cloud 組織に関連付けることができ、組織と請求 ID の間には必ずしも 1 対 1 の関係はありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ログイン会社 </p> </td> 
   <td colname="col2"> <p>1 つの請求会社が<a href="https://helpx.adobe.com/jp/analytics/kb/multiple-login-companies.html">複数のログイン会社</a>を持つことができます。企業が使用するレポートスイートの集まりです。企業によっては、複数のログイン会社名を持ち、組織内の異なる部署に適用します。この機能は特に、様々な事業単位を扱う大きな組織で、多くのレポートスイートが社内の他の従業員には適用されない場合に便利です。 </p> <p>多くの場合、これらは会社の地域子会社です。以下に、ログイン会社とそれらに関連するレポートスイートの例を示します。 </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide：RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us：RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in：RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de：RS4 </li> 
    </ul> <p>注意：請求会社内の<u>全</u>レポートスイートのサーバーコール使用状況データは、適切な<a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">権限</a>を持つすべてのユーザーから参照できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud 組織 </p> </td> 
   <td colname="col2"> <p> 組織は、管理者がグループおよびユーザーの設定や、Experience Cloud でのシングルサインオンの制御をおこなえるエンティティです。組織は、すべての Experience Cloud 製品およびソリューションをまたいだログイン会社のように機能します。 </p> <p>ほとんどの場合、組織は、会社名です。ただし、会社は多数の組織を持つことができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバーコールのコミットメント </p> </td> 
   <td colname="col2"> <p>会社がアドビと契約を結ぶと、アドビのセールスチームは、担当者、顧客、タイプ（プライマリ、セカンダリ、モバイルプライマリ、モバイルセカンダリ）、契約期間中に使用できるサーバーコールの概数を決定します。これがサーバーコールの合計コミットメントになります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用期間 </p> </td> 
   <td colname="col2"> <p>サーバーコールの使用状況を監視するために、この合計サーバーコールコミットメントはより短い使用期間（3 ヶ月など）に分けられ、前年との比較を実行しやすくなっています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>契約期間 </p> </td> 
   <td colname="col2"> <p>契約期間は複数年にわたることがあります。例えば、会社のサーバーコールコミットメントが 3 年契約で 600 万コールだとしましょう。サーバーコールの使用状況を監視するために、この 3 年間をより短い使用期間に分けて、前年との比較を実行しやすくすることができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## サーバーコールの使用状況に関する権限 {#section_FCC58EB635954A32990D4E67B52B4369}

サーバーコールの使用状況に関する権限は Analytics 管理者に自動的に付与されます。これにより、管理者はダッシュボードの表示やサーバーコールアラートの作成をおこなえます。管理者は、この権限を管理者以外のユーザーに付与することもできます。

>[!NOTE]
>
>会社は、サーバーコールの使用状況にアクセスできるログイン会社を選ぶことができます。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 権限名 </th> 
   <th colname="col3" class="entry"> Adobe Analytics にログインしている場合の権限の付与（従来のログイン） </th> 
   <th colname="col4" class="entry"> Adobe Experience Cloud にログインしている場合の権限の付与 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>サーバーコールの使用状況 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">sc.omniture.com を通じて Analytics にログインします。 </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A"><span class="ignoretag"> <span class="uicontrol">管理者</span> / <span class="uicontrol">すべての管理者</span> / <span class="uicontrol">ユーザー管理</span> / <span class="uicontrol">グループ</span> / <span class="uicontrol">全レポートアクセスを編集</span> / <span class="uicontrol">分析ツール</span> &gt; <span class="uicontrol"> </span>のカスタマイズ&gt; <span class="uicontrol">サーバーコールの使用状況</span> </span> </li> 
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
