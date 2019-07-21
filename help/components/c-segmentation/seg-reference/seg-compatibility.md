---
description: セグメントビルダーで作成するすべてのセグメントが Data Warehouse と互換性があるとは限りません。サポートされる機能を次の表に示します
seo-description: セグメントビルダーで作成するすべてのセグメントが Data Warehouse と互換性があるとは限りません。サポートされる機能を次の表に示します
seo-title: Data Warehouse セグメントの互換性
solution: Analytics
title: Data Warehouse セグメントの互換性
topic: セグメント
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: 26bba9528873c983852754056a5495c4004d25e6

---


# Data Warehouse セグメントの互換性

Not all segments created in the Segment Builder are compatible with [!DNL Data Warehouse]. サポートされる機能を次の表に示します

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis </th> 
   <th colname="col3" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>除外</b> </td> 
   <td colname="col2"> あらゆるレベルでサポート。 </td> 
   <td colname="col3"> トップレベルの特殊なケースでのみサポート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>順次セグメント</b> </td> 
   <td colname="col2"> サポート。 </td> 
   <td colname="col3"> サポートなし。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>AND と OR の無制限の結合</b> </td> 
   <td colname="col2"> サポート。 </td> 
   <td colname="col3"> 一部制限。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンテナのネスト</b> </td> 
   <td colname="col2"> サポート。 </td> 
   <td colname="col3"> 一部制限（スコープを狭くする必要があります。例えば、訪問者はヒットを含めることができるが、その逆はできません）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディメンション</b> </td> 
   <td colname="col2">セグメントビルダーの<span class="uicontrol">定義</span>フィールドにディメンションをドラッグ＆ドロップして、プロトコルの互換性を調べます。例えば、以下のディメンションは、Analysis Workspace、Reports&amp; AnalyticsおよびAd Hoc Analysisでのみサポートされています。 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">入口サーバー </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">入口カテゴリ </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">エントリ日 </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">すべての検索ページのランク </li> 
    </ul> </td> 
   <td colname="col3"> セグメントビルダーの<span class="uicontrol">定義</span>フィールドにディメンションをドラッグ＆ドロップして、プロトコルの互換性を調べます。例えば、次のディメンションは、Data Warehouse でのみサポートされます。 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">IP アドレス </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">ページ URL </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">訪問者 ID </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">Experience Cloud 訪問者 ID </li> 
    </ul> <p>The following dimensions <b>cannot </b>be used in Data Warehouse segments: </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">すべての検索ページのランク </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">午前 / 午後 </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">月間通算日 </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">曜日 </li> 
     <li id="li_4008565353084611BD782B98D50C0611">年間通算日 </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">入口ビジネスユニット </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">入口（「入口ページ」を除く、「入口」で始まるすべてのディメンション） </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">出口（「出口リンク」および「出口ページ」を除く、「出口」で始まるすべてのディメンション） </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">階層（「階層」で始まるすべてのディメンション） </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">ヒットの深さ </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">ヒットタイプ </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">時刻 </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">年間通算月 </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">エラーページ（404） </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">有料検索 </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">四半期 </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">再来訪頻度 </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">直帰数 </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">イベント前の時間 </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">ページでの滞在時間 - グループ </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">訪問別滞在時間 - グループ </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">トラッキングオプトアウト理由 </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">米国の州 </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">平日 / 週末 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>セグメントの積み重ね</b> </td> 
   <td colname="col2"> サポート。 </td> 
   <td colname="col3"> サポートなし。 </td> 
  </tr> 
 </tbody> 
</table>

