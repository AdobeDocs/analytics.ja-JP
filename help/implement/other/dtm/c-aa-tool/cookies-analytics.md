---
description: Adobe Analytics に Dynamic Tag Management をデプロイする際に使用される Cookie のグローバル設定に関するフィールドの説明です。
keywords: Dynamic Tag Management, cookie, 訪問者 id, 訪問者名前空間, ドメインピリオド, fp ドメインピリオド, トランザクション id, cookie の有効期限
solution: Experience Cloud,Analytics
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: 1ff9c892670e7b120bf727e556ff70f76c6751be
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 82%

---


# Cookie

Adobe Analytics に [!UICONTROL Dynamic Tag Management] をデプロイする際に使用される Cookie のグローバル設定に関するフィールドの説明です。

*`Property`*／ツールを編集／Cookie

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 訪問者 ID </td> 
   <td colname="col2"> <p>オンラインとオフラインの両方のシステムに存在する顧客を表す一意の値。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者名前空間 </td> 
   <td colname="col2"> <p>Cookie の設定場所であるドメインを識別する変数。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> ドメインピリオド </td> 
   <td colname="col2"> <p>ページ URL のドメイン内のピリオド数を指定することで、Analytics の Cookie である <code> s_cc</code> と <code> s_sq</code> を設定するドメインが決定されます。この変数は、一部のプラグインで、プラグインの cookie を設定するための適切なドメインを決定する際にも使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP ドメインピリオド数 </td> 
   <td colname="col2"> <p>   <span class="term"> fpDomainPeriods変数は、導入でサードパーティのadobedc.</span> netdomainまたは従来の<code> s_sq</code>（依然として有効）2o. <code> s_cc</code>netor  <span class="filepath"> omdomcookie omdc.netdomainsが使用されている場合でも、JavaScript(</span>  <span class="filepath"> </span>  <span class="filepath"> </span> 、プラグイン)によって設定されたcookie用に使用されます。 </p> <p><a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  >s.fpCookieDomainPeriods</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トランザクション ID </td> 
   <td colname="col2"> <p>オフラインアクティビティを導いたオンライントランザクションを表す一意の値。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie の有効期限 </td> 
   <td colname="col2"> <p>Cookie の存続期間を決定します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

