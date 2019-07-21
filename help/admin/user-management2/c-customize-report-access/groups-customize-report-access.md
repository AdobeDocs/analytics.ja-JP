---
description: Analytics ツール、レポートスイートツール、指標およびディメンションに対するグループ権限をカスタマイズします。
keywords: グループ;permissions
seo-description: Analytics ツール、レポートスイートツール、指標およびディメンションに対するグループ権限をカスタマイズします。
seo-title: レポートアクセスのカスタマイズ-概要
solution: Analytics
subtopic: ユーザーとグループ
title: レポートアクセスのカスタマイズ-概要
topic: 管理ツール
uuid: 818a7196-8b43-4654-8d5f-800b3122aad3
translation-type: tm+mt
source-git-commit: f608acafd77fd6469f553f30c45f54484028890a

---


# レポートアクセスのカスタマイズ-概要

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). ユーザーを移行する時期は、アドビから通知されます。After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

Analytics ツール、レポートスイートツール、指標およびディメンションに対するグループ権限をカスタマイズします。

**[!UICONTROL 新しいグループ]** を追加/ **[!UICONTROL レポートアクセス]**

[!UICONTROL ユーザーグループの定義]ページの「[!UICONTROL レポートアクセス]」セクションは、詳細なレベルで権限をカスタマイズすることを可能にするアクセスカテゴリを提供します。

![](assets/report-access.png)

例えば、特定の指標およびディメンション（eVar を含む）およびセグメントや計算指標の作成などの機能に対する権限を持つ、複数の Analytics ツール（[!UICONTROL Analysis Workspace]、[!UICONTROL Reports &amp; Analytics] および [!UICONTROL Report Builder]）へのアクセス権を持つグループを作成できます。

## 権限について知っておくべきこと {#section_3D25D4A5BD044008870C5B98F696244E}

<table id="table_DB7806E05E2040EC9A4CB7C3596879EC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>管理者アクセス／定義済みのグループ </p> </td> 
   <td colname="col2"> <p> 管理者には、定義済みのグループは不要になりました。管理者は、すべての項目（ツール、指標、ディメンション）に加え、Web サービス、Report Builder、Activity Map、Ad Hoc Analysis にアクセスできるようになりました。 </p> <p>グループの目的は、管理者以外のユーザーにアクセスを付与または制限することです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムグループ </p> </td> 
   <td colname="col2"> <p> カスタムグループが、定義済みのグループから置き換わりました。既存の定義済みグループは、同じグループ名を使用して、カスタムグループに移行されます。作成したカスタムグループは、その設定も含めて保持されます。ただし、設定の場所が移動されることに注意してください。例えば、（Admin Console のカスタマイズの）カンパニー設定は、現在は、<a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local">Analytics ツールのカスタマイズ</a>にあります。 </p> <p> Users belonging to <span class="term"> All Report Access</span> have been migrated to a custom group with access to: </p> 
    <ul id="ul_7E1B443DEEF7452E85FEB30CA0BBC8BE"> 
     <li id="li_A510C2A4129340E0AB08EEBDBE4AEAD9">すべてのディメンション </li> 
     <li id="li_8BA1D7A2527C4F10AC93108B9E87F418">すべての指標 </li> 
     <li id="li_265830A2C6B94AF28720DA99980EAA51">すべてのレポートスイート </li> 
     <li id="li_685B99DEAB814D7B9C11B14AA4CB8CD4">チャネルレポート </li> 
     <li id="li_B35420302AAB42509BD6AF0FA6349BF8">異常値検出 </li> 
     <li id="li_3787E4696C454D3ABD1D75F6C282A9A2">リアルタイムレポート </li> 
     <li id="li_3797DF9C40D1426588819116362962F5">Analysis Workspace アクセス </li> 
    </ul> <p>定義済みのグループで以前に使用可能だったすべての設定がユーザーグループの定義<span class="wintitle">の「</span>レポートアクセス</a>」設定でカスタマイズに利用できるので、管理者は、カスタムグループを削除して、独自のものを作成できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディメンションレベルの権限 </p> </td> 
   <td colname="col2"> <p>権限をカスタマイズして、（指標に加えて）ディメンションへのアクセス権を含めたり、除外したりできます。 </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>カスタムグループ内にあるすべてのディメンションと指標は新しいカテゴリに自動的に移行されます。既存のグループで指標が有効な場合、新しく権限を付与できるすべてのディメンション（eVar およびコンテンツに対応するもの）および指標は、デフォルトで有効になります。 </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> 分類インポーター（以前の SAINT）の権限：分類へのアクセスは、分類の基となる<a href="https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html" format="html" scope="external">変数</a>へのアクセスによって判断されます。 </li> 
    </ul> <p>See <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Customize Dimension Permissions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://helpx.adobe.com/enterprise/using/admin-console.html" format="html" scope="external"> Adobe Admin Console</a> </p> </td> 
   <td colname="col2"> <p>新規のお客様または <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html" format="html" scope="external">Experience Cloud でプロビジョニングされた</a>会社を持つお客様の場合にのみお勧めします。既存の <span class="keyword">Analytics</span> のお客様の <span class="keyword">Experience Cloud</span> ID 管理システムへの移行は、予定されています。 </p> <p>More information is available in <a href="https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/" format="html" scope="external"> Analytics User Migration to the Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンテンツ対応 </p> </td> 
   <td colname="col2"> <p>コンテンツ対応には、Experience Cloud ソリューション統合に関連した指標に関する権限を管理できる変数が含まれます。<span class="keyword">Social</span>、<span class="keyword">Mobile</span> または <span class="keyword">Experience Cloud</span> 統合全体に挿入されたその他のデータに関する権限を管理できます。これらは、デフォルトで有効になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用されなくなった権限／レポート </p> </td> 
   <td colname="col2"> <p>これらの古いレポートは削除されます。 </p> 
    <ul id="ul_C0415CFF0562472297272EC58ECC0774"> 
     <li id="li_62B1CE33B1454987B878B321EB40D62E">月別サマリ </li> 
     <li id="li_71CD776D212540A18F9B083D2E11A296">訪問者ホームページ </li> 
     <li id="li_406200AD68C74D11B5F53988A4E76A68">Netscape プラグイン </li> 
     <li id="li_A124637D69C94C78921C8B028D890541">主要訪問者 </li> 
     <li id="li_5C26FF95371B4F3080FF75C7F8DE0F72">主要訪問者が閲覧したページ </li> 
     <li id="li_E7E262BD0CF64E16B838F995F6A13B8A">訪問者スナップショット </li> 
     <li id="li_0EDC74625C0D4B1A992FCA49B648E4C0">DRM </li> 
     <li id="li_ACC92E6EA188409486E7C943F26B9DAC">通信方式 </li> 
     <li id="li_6E18C4D12377416A8124BBD13164B03A">Java バージョン </li> 
     <li id="li_1599265E59EF4F34BB406356410C9E68">ブックマーク URL の長さ </li> 
     <li id="li_3035442010984C409089B21E03DB7BCC">機体番号送信 </li> 
     <li id="li_6B2163ED8FC84EBF933D97A504B4D527">PTT </li> 
     <li id="li_0EB8A4A7619B45DF87109B183A7C69C8">デコメ対応 </li> 
     <li id="li_989FAC662F7344E6BDDC517B79D4581E">情報 </li> 
     <li id="li_F1FB7F8E415443F3B63F6D11D59A04AB">情報サービス </li> 
    </ul> <p>これらのレポートは、 </p> 
    <ul id="ul_F71505C59F734EA9B541BF8AB9F9388F"> 
     <li id="li_7D461907B895447280E69CF1520DF47C">引き続きブックマークからアクセスできます。 </li> 
     <li id="li_27BA2DD6BA4C446FBAA06B6C76CD171F">新しいディメンション権限カテゴリに含まれません。 </li> 
     <li id="li_504E9D8421714406A0F37DEF1E10E34B">権限の編集はできません。 </li> 
     <li id="li_0022E8DCA07344C793847E8282EFBEEF">現在アクセスできるカスタムグループへのアクセスを保持します。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

