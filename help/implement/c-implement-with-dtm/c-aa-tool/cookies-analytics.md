---
description: Adobe Analytics に Dynamic Tag Management をデプロイする際に使用される Cookie のグローバル設定に関するフィールドの説明です。
keywords: Dynamic Tag Management;cookies；訪問者ID；訪問者名前空間；ドメインピリオド数；fpドメインピリオド数；トランザクションID;cookieの有効期間
seo-description: Adobe Analytics に Dynamic Tag Management をデプロイする際に使用される Cookie のグローバル設定に関するフィールドの説明です。
seo-title: Cookie
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Cookie

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Cookies]**

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
   <td colname="col2"> <p>ページ URL のドメイン内のピリオド数を指定することで、Analytics の Cookie である <code>s_cc</code> と <code>s_sq</code> を設定するドメインが決定されます。この変数は、一部のプラグインで、プラグインの cookie を設定するための適切なドメインを決定する際にも使用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP ドメインピリオド数 </td> 
   <td colname="col2"> <p>Folio Builder <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>s.fpCookieDomainPeriods <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> を参照してください</a>。 </p> </td> 
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

