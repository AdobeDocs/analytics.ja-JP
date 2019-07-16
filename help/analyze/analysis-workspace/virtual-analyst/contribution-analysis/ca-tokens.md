---
description: 'null'
seo-description: 'null'
seo-title: 貢献度分析の概要
title: 貢献度分析の概要
uuid: 2bd295b0- c5ce-4443-86af-024efd20c021
translation-type: tm+mt
source-git-commit: 10050f2021e1e78e4e258255d356d119aba960c1

---


# 貢献度分析の概要

## Contribution Analysis Tokens - overview {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

>[!IMPORTANT]
>
>貢献度分析は、Reports&amp; Analytics機能セットから削除されました。現在は、Analysis Workspaceからのみ利用できます。

貢献度分析の権限を持つすべてのお客様は、Analysis Workspace 内で、毎月限られた回数だけ完全な貢献度分析を実行できます。ただし、特定の製品（SiteCatalyst 15）をご利用のお客様や、Analytics Foundation をご利用のお客様、Analytics Select をご利用のお客様は **除外** されます。これらに該当するお客様は、貢献度分析を実行できません。

会社ごとの実行回数は、会社が購入した Adobe Analytics 製品の種類に基づいて付与される月ごとのトークンによって制限されます。これには、貢献度分析へのアクセスを制限して、トークンの誤用を避ける効果があります。

## よくある質問（FAQ） {#section_11D0431AD2014B96AB9561CA66A367CE}

<table id="table_357775E5058644099E26B15A6790E8AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>アドビがトークンを導入した理由</b> </p> </td> 
   <td colname="col2"> <p>貢献度分析は、2015 年のリリース以降、Adobe Analytics の最も重要な機能の 1 つになりました。一部の Analytics 製品のようにディメンション数を 3 つに制限するのではなく、ごく限られた回数でも 1 ヶ月に何度か「完全な」機能を実行できるようにすることで、制限のない完全な貢献度分析のメリットを実感していただけるものと考えています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>貢献度分析のトークンはどのように機能しますか。プロジェクトに既存の貢献度分析を実装するときもトークンが必要ですか。それとも、新しい貢献度分析を実行するときにのみ、トークンが必要ですか。</b> </p> </td> 
   <td colname="col2"> <p>各ログイン会社（各ユーザーではなく）は、1 ヶ月あたり定められた数のトークンを入手します。これらのトークンを使用して、Analysis Workspace 内で「完全な」貢献度分析を実行できます。 </p> <p>新しい貢献度分析を生成するたびにトークンが 1 つ必要です。事前実行された貢献度分析をプロジェクトに実装するときは、トークンは不要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Reports &amp; Analytics での貢献度分析にトークンは適用されますか。</b> </p> </td> 
   <td colname="col2"> <p>いいえ。2018 年 4 月リリースより、Reports &amp; Analytics で貢献度分析が提供されなくなりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>トークンを切らしていますが、さらに貢献度分析を実行したい場合はどうしますか。</b> </p> </td> 
   <td colname="col2"> <p>別の Adobe Analytics 製品にアップグレードします。例えば、Standard（2 トークン／月）から Ultimate（20 トークン／月）にアップグレードします。トークンを追加購入することはできません。既存のパッケージフレームワーク内でアップグレードする必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>貢献度分析へのアクセスを制限するには、どのようにしますか。</b> </p> </td> 
   <td colname="col2"> <p>By default, only admins have access to run Contribution Analyses, but admins can grant access to other users by creating a permission group in the <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html" format="html" scope="external"> Admin Console </a>. 貢献度分析を使用する権限を持つユーザーのみに対して、貢献度分析を使用する権限を与え、アクセスを不正にしないことを信頼する必要があります。 </p> <p>この権限は、<span class="ignoretag"><span class="uicontrol">Analytics</span>／<span class="uicontrol">管理者</span>／<span class="uicontrol">ユーザー管理ホーム</span>／<span class="uicontrol">グループの編集</span>／<span class="uicontrol">全レポートアクセスを編集</span>／<span class="uicontrol">レポートスイートツールをカスタマイズ</span>／<span class="uicontrol">ツールとレポート</span></span>では「貢献度分析」と呼ばれています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>1 ヶ月あたり使用可能なトークン数は、どうすればわかりますか。また、当月に使用したトークン数は、どうすればわかりますか。</b> </p> </td> 
   <td colname="col2"> <p><span class="ignoretag"><span class="uicontrol">管理者</span>／<span class="uicontrol">会社設定</span>／<span class="uicontrol">機能アクセスレベルを表示</span></span>を選択します。以下のページに、新しい項目が 2 つあります。 </p> <p><img placement="break"  src="assets/ca_access_level.png" id="image_16012FE1162C485EA768D175F43D7563" width="500px" /> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Anomaly Detection and Contribution Analysis entitlements {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

Analysis Workspace における異常値検出と貢献度分析の詳細な権限のリストを以下に示します。

>[!IMPORTANT]
>
>異常値検出と貢献度分析は、Reports &amp; Analytics の画面から削除され、現在は、Analysis Workspace からのみ使用できます。Adobe Analytics Select および Adobe Analytics Foundation をご利用のお客様は、ワークスペースで「毎日の精度」の異常値検出のみにアクセスできます。

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Analytics の権限 </th> 
   <th colname="col2" class="entry"> 異常値検出 </th> 
   <th colname="col3" class="entry"> 貢献度分析 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>毎日の精度のみ </p> </td> 
   <td colname="col3" colsep="1"> <p>トークンなし </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other" format="html" scope="external">Select</a> </p> </td> 
   <td colname="col2"> <p>毎日の精度のみ </p> </td> 
   <td colname="col3"> <p>トークンなし </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other" format="html" scope="external">Prime</a> </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 ヶ月あたり 10 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other" format="html" scope="external"> Ultimate</a> </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 ヶ月あたり 20 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>トークン数に制限なし </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 ヶ月あたり 2 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium（360、Attribution） </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>1 ヶ月あたり 2 トークン </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium（Complete、<a href="https://www.adobe.com/data-analytics-cloud/analytics/predictive-intelligence.html" format="html" scope="external">Predictive Intelligence</a>） </p> </td> 
   <td colname="col2"> <p>○ </p> </td> 
   <td colname="col3"> <p>トークン数に制限なし </p> </td> 
  </tr> 
 </tbody> 
</table>
