---
description: Adobe Analytics に Dynamic Tag Management をデプロイする際に使用される Cookie のグローバル設定に関するフィールドの説明です。
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
   <td colname="col2"> <p><span class="term"> fpCookieDomainPeriods</span> 変数は、実装でサードパーティ <span class="filepath">2o7.net</span> または <span class="filepath">omtrdc.net</span> ドメインが使用されている場合でも、JavaScript（<code> s_sq</code>、<code> s_cc</code>、プラグイン）によって設定された本質的にファーストパーティの Cookie 用に使用されます。 </p> <p>「<a href="/help/implement/js-implementation/c-variables/configuration-variables.md"  >s.fpCookieDomainPeriods</a>」を参照してください。 </p> </td> 
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

