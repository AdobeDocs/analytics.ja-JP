---
description: 各訪問における訪問者の参照サイトを追跡して記録することで、各訪問で訪問者がどのようにしてサイトを見つけたかを知ることができます。
seo-description: 各訪問における訪問者の参照サイトを追跡して記録することで、各訪問で訪問者がどのようにしてサイトを見つけたかを知ることができます。
seo-title: リファラータイプ
solution: Analytics
title: リファラータイプ
topic: レポート
uuid: 7f63d327- d223-4537- a722-4780aae05c2b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# リファラータイプ

各訪問における訪問者の参照サイトを追跡して記録することで、各訪問で訪問者がどのようにしてサイトを見つけたかを知ることができます。

以下のリストに、様々なタイプのリファラーの定義を示します。

**その他の Web サイト**：訪問者が他の Web サイト（訪問先サイトの一部として定義されていない）上のページに配置されたリンクをクリックして目的の Web サイトにアクセスした場合は、このリファラーが記録されます。

**検索エンジン**：訪問者が検索エンジンを使用してサイトにアクセスした場合は、検索エンジンリファラーが記録されます。参照値はアドビによって検索エンジンと見なされる必要があり、検索エンジンと見なされないサブドメインにすることはできません（例えば、[!DNL mail.yahoo.com] は電子メールで使用されるドメインなので検索エンジンではありません）。

**[!UICONTROL ソーシャルネットワーク]**：参照値は、Adobe によりソーシャルネットワークと見なされる必要があります。[ソーシャルネットワークのリスト](https://helpx.adobe.com/analytics/kb/list-social-networks.html)を参照してください。

**電子メール**:訪問者がプロトコル [!DNL imap://] を含む電子メールメッセージリンクをクリックしてサイトに来訪した場合、参照ドメインは電子メール参照 [!DNL mail://] ドメインと見なされます。例えば [!DNL https://mail.yahoo.com] からの訪問は、プロトコルが [!DNL https://] :// なので、電子メールリファラーとしてカウントされません。Outlook からの電子メールは「手動入力 / ブックマーク」行に表示されますが、ドメインが既知の検索エンジンである HTTP プロトコルを含むリファラーはすべて「検索エンジン」行に表示されます。

**手動入力/ブックマーク**：訪問者がサイトの URL をブラウザーに手動入力するか、ブックマークを選択してサイトにアクセスした場合は、このリファラーが記録されます。訪問の最初のヒットでリファラーがない場合、モバイルデバイスは&#x200B;*`typed/bookmarked`*&#x200B;のリファラータイプをレポートします。

**[!UICONTROL サイト内]**：これらの項目は、内部 URL フィルターによってタグ付けされた URL です。These items are not counted as *`referrer instances`* but can be seen when reporting on other metrics.

## インターフェイスごとのリファラータイプ {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reports &amp; Analytics（SiteCatalyst） </th> 
   <th colname="col3" class="entry"> ad hoc analysis </th> 
   <th colname="col4" class="entry"> data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> レポートされるリファラータイプ </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">その他の Web サイト </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> 検索エンジン </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> ソーシャル </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> 手動入力/ブックマーク </li> 
    </ul> <p> このレポートには、インスタンスと実訪問者数の 2 つの定義済みの指標が表示されます。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">その他の Web サイト </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> 検索エンジン </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> ソーシャル </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> 手動入力/ブックマーク </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">その他の Web サイト </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> 検索エンジン </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> ソーシャル </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> 手動入力/ブックマーク </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> サイト内 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## メモ {#section_B83A3571D64E4E7792712FAF740D7955}

* リファラー、リファラータイプおよび参照ドメインは、訪問の最初のヒット時に設定されます。リファラーが外部の場合（例えば、訪問者がサイトから出て、検索エンジンを使用して最初の訪問の有効期限が切れるまでに直前のサイトに戻った場合）は、これらの値は訪問中に設定されます。これらの値は同時に設定され、訪問間で保持されます。
* このレポートには、すべてのリファラータイプは一覧表示されません。つまり、サイト全体の訪問はこのレポートの訪問と一致しません。

## レポート履歴 {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| 日付 | 変更 |
|---|---|
| 2014 年 1 月 16 日 | data warehouse が Reports &amp; Analytics で使用されるロジックと一致するように更新されました。これまで、リファラータイプは訪問間で保持されませんでした。 |

