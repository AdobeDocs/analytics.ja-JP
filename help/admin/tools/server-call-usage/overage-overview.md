---
description: Adobe Analytics サーバーコールの使用機能の概要です。
title: サーバーコールの使用状況の概要
feature: Server Call Usage
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
role: Admin
TQID: https://experienceleague.adobe.com/-IIz9r-K-flZq85Dz3lhYuo9-Ko0zt0KoJJ7DtI5Mz4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1013
ht-degree: 27%

---

# サーバーコールの使用状況

Adobe Analytics server call usageは、ブラウザーとモバイルサーバーコールの両方の使用状況データに対する透明性のリクエストに対応します。 次の項目にアクセスできます。

* サーバーコール使用データを追跡し、契約上の制限と比較するサーバーコール使用ダッシュボード。 （Adobe Analyticsで、> [!UICONTROL **管理者**] > [!UICONTROL **サーバーコールの使用状況**]&#x200B;を選択します）
* アラートビルダーのサーバーコール使用状況アラートタイプで、超過を防ぐためのアラートを設定できます（Adobe Analyticsでは、[!UICONTROL **コンポーネント**]/[!UICONTROL **アラート**]&#x200B;を選択します）

サーバーコールの使用の主な利点は次のとおりです。

* 契約上のサーバーコール使用制限に対するモバイルの使用を含め、サーバーコールの使用とコミットメントのデータを&#x200B;**可視性**&#x200B;で確認できます。
* **超過のリスクまたは発生を通知し、超過発生の可能性に備えて/対処するためのアラート**&#x200B;です。

## 前提条件 {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **権限：** サーバーコール使用状況ダッシュボードとアラートビルダーまたはアラートマネージャーにアクセスするには、Adobe Analytics Administratorである必要があります。
* **権限：**&#x200B;管理者は管理者以外のユーザーにアクセス権を付与できます。この権限は&#x200B;**[!UICONTROL サーバー呼び出しの使用状況]**&#x200B;と呼ばれます。 [&#x200B; サーバー呼び出し使用権限](#server-call-usage-permission)を参照してください。

## 重要な用語 {#terminology}

サーバーコールの使用状況を理解するには、次の用語が重要です。

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
   <td colname="col2"> <p>「ヒット」または「イメージリクエスト」とも呼ばれます。処理するデータをアドビのサーバーに送信するインスタンスです。 最も一般的なタイプのサーバーコールはページビューです。 ページビューでは、訪問者が Web サイトのページを閲覧し、アドビ向けのサーバーコールが生成されます。アドビでは、情報が収集されて処理され、レポート指標に含まれます。 </p> <p>離脱リンクやファイルのダウンロードなど他のタイプのサーバーコールでは、データが処理のためにアドビに送信されますが、新規ページビューとしては記録されません。 ページビューを「除外」した場合でも（例えば、設定したIP アドレス範囲によってレポートから除外された場合）、Adobeで受信および処理されても、レポートには表示されないため、サーバーコールになります。 </p> <p><b>プライマリサーバーコール </b>: web サイトの訪問者ブラウザーまたはData Insertion APIから直接受信したリクエスト。 プライマリヒット（ページビュー）、プライマリカスタムイベント、プライマリダウンロードイベント、プライマリ終了イベントが含まれます。 </p> <p><b>セカンダリサーバーコール </b>：マルチスイートタグによって作成された、またはVISTA ルールによってコピー/移動されたプライマリサーバーコールのコピー。 セカンダリサーバーコールがVISTA ルールによって別のレポートスイートに移動（コピーされない）場合、累積されたセカンダリコールはプライマリサーバーコールから差し引かれます。 </p> <p><b> モバイルプライマリサーバーコール </b> </p> <p>いずれかの Mobile SDK から直接受け取ったリクエスト。 これには、trackAction、trackState、trackApp Crashes、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrease が含まれます。</p> <p><b> モバイルセカンダリサーバーコール </b> </p> <p>複数のスイートのタグによって作成されたか、Vista ルールによってコピー／移動されたプライマリサーバーコールのコピーです。 セカンダリサーバーコールがVISTA ルールによって別のレポートスイートに移動（コピーされない）場合、累積されたセカンダリコールはプライマリサーバーコールから差し引かれます。 </p> <p>注意：契約上、モバイルサーバーコール（プライマリまたはセカンダリ）しか使用できない場合、Web 限定の使用量もモバイル限定の使用量もモバイル限定コミットメントの分としてカウントされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>請求会社（請求ID） </p> </td> 
   <td colname="col2"> <p>サーバーコールに対して請求される法人。 例：adobe.com 各請求会社には請求 ID があり、これを使用して請求先顧客を一意に識別します。 請求IDは、複数のCX Enterprise組織に関連付けることができます。組織と請求IDの間には必ずしも1:1の関係があるわけではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ログイン会社 </p> </td> 
   <td colname="col2"> <p>1 つの請求会社が<a href="https://helpx.adobe.com/jp/analytics/kb/multiple-login-companies.html">複数のログイン会社</a>を持つことができます。 ログイン会社は、組織で使用されるレポートスイートのコレクションです。 一部の組織では、複数のログイン企業が組織の様々な部分に適用されています。 これは、多くのレポートスイートが社内の他のグループには適用されない、異なる事業部門を扱う大規模組織で特に便利です。 </p> <p>多くの場合、これらは企業の地域の子会社です。 次の例は、ログイン会社と関連するレポートスイートを示しています。 </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide:RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>注意：請求会社内の<u>全</u>レポートスイートのサーバーコール使用状況データは、適切な<a href="/help/admin/tools/server-call-usage/overage-overview.md">権限</a>を持つすべてのユーザーから参照できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CX Enterprise組織 </p> </td> 
   <td colname="col2"> <p>組織とは、管理者がグループとユーザーを設定し、CX Enterpriseでのシングルサインオンを制御できるようにするエンティティです。 組織は、すべてのCX Enterprise製品とソリューションにまたがるログイン企業のように機能します。 </p> <p>ほとんどの場合、組織は勤務先の会社名です。 ただし、1 つの会社が多くの組織を持つことができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバーコールのコミットメント </p> </td> 
   <td colname="col2"> <p>お客様がAdobeと契約を締結すると、Adobe営業部門は、お客様、お客様、種類（プライマリ、セカンダリ、モバイルプライマリ、モバイルセカンダリ）および契約期間中に発生すると予想されるサーバーコールの概数を特定します。 これは、サーバー呼び出しの合計コミットメントです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用期間 </p> </td> 
   <td colname="col2"> <p>サーバーコールの使用状況モニタリングの目的で、このサーバーコールの合計コミットメントは、前年比での比較を容易にするために、より短い使用期間（3か月など）に分割されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>契約期間 </p> </td> 
   <td colname="col2"> <p>契約期間は複数年にわたることがあります。 例えば、3年間の契約期間で600万件のサーバーコールを処理するとします。 サーバーコールの使用状況を監視するために、この 3 年間をより短い使用期間に分けて、前年との比較を実行しやすくすることができます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## サーバーコールの使用権限 {#permission}

サーバーコールの使用権限は、Analytics管理者に自動的に付与されます。 ユーザーはダッシュボードを表示し、サーバー呼び出しアラートを作成できます。 管理者は、この権限を管理者以外のユーザーに付与することを選択できます。

>[!NOTE]
>
>会社は、どのログイン会社がサーバーコールの使用にアクセスできるかを選択できます。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 権限名 </th> 
   <th colname="col3" class="entry"> Adobe Analytics（従来のログイン）にログインしている場合は、権限を付与してください </th> 
   <th colname="col4" class="entry"> Adobe CX Enterpriseにログインしている場合は、権限を付与します </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>サーバーコールの使用状況 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">sc.omniture.comを介してAnalyticsにログインします。 </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A"><span class="ignoretag"> <span class="uicontrol">管理者</span> &gt; <span class="uicontrol">すべての管理者</span> &gt; <span class="uicontrol"> ユーザー管理</span> &gt; <span class="uicontrol"> グループ </span> &gt; <span class="uicontrol">すべてのレポートアクセスを編集</span> &gt; <span class="uicontrol"> Analytics ツール </span> &gt; <span class="uicontrol"> </span>をカスタマイズ &gt; <span class="uicontrol"> サーバーコールの使用状況</span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">login.experiencecloud.adobe.com にログインします。</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">「<span class="uicontrol">Analytics</span>」をクリックします。 </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF"><span class="ignoretag"> <span class="uicontrol">製品</span> &gt; <span class="uicontrol">製品プロファイル </span> &gt; <span class="uicontrol">権限</span> &gt; <span class="uicontrol">分析ツール </span> &gt; <span class="uicontrol"> サーバーコール使用状況</span> </span>に移動します </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
