---
description: Analytics ツール、レポートスイートツール、指標およびディメンションに対するグループ権限をカスタマイズします。
keywords: グループ;権限
subtopic: Users and groups
title: レポートアクセスのカスタマイズ - 概要
topic: 管理ツール
uuid: 818a7196-8b43-4654-8d5f-800b3122aad3
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 96%

---


# レポートアクセスのカスタマイズ - 概要

>[!IMPORTANT]
>
>ユーザーと製品の管理は [Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移動しました。すべての顧客が移行されたら、**[!UICONTROL Analytics]**／**[!UICONTROL 管理ツール]**／**[!UICONTROL ユーザー管理]**&#x200B;のヘルプコンテンツは利用できなくなります。

Analytics ツール、レポートスイートツール、指標およびディメンションに対するグループ権限をカスタマイズします。

**[!UICONTROL 新しいグループを追加]**／**[!UICONTROL レポートアクセス]**

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
   <td colname="col2"> <p> 管理者には、定義済みのグループは不要になりました。管理者は、すべての項目（ツール、指標、ディメンション）に加え、Webサービス、Report BuilderおよびActivity Mapにアクセスできるようになりました。 </p> <p>グループの目的は、管理者以外のユーザーにアクセスを付与または制限することです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムグループ </p> </td> 
   <td colname="col2"> <p> カスタムグループが、定義済みのグループから置き換わりました。既存の定義済みグループは、同じグループ名を使用して、カスタムグループに移行されます。作成したカスタムグループは、その設定も含めて保持されます。ただし、設定の場所が移動されることに注意してください。例えば、（Admin Console のカスタマイズの）カンパニー設定は、現在は、<a href="/help/admin/user-management2/c-customize-report-access/groups-analytics-tools.md">Analytics ツールのカスタマイズ</a>にあります。 </p> <p> 「<span class="term">すべてのレポートアクセス</span>」に属するユーザーは、次のアクセス権を持つカスタムグループに移行されました。 </p> 
    <ul id="ul_7E1B443DEEF7452E85FEB30CA0BBC8BE"> 
     <li id="li_A510C2A4129340E0AB08EEBDBE4AEAD9">すべてのディメンション </li> 
     <li id="li_8BA1D7A2527C4F10AC93108B9E87F418">すべての指標 </li> 
     <li id="li_265830A2C6B94AF28720DA99980EAA51">すべてのレポートスイート </li> 
     <li id="li_685B99DEAB814D7B9C11B14AA4CB8CD4">チャネルレポート </li> 
     <li id="li_B35420302AAB42509BD6AF0FA6349BF8">異常値検出 </li> 
     <li id="li_3787E4696C454D3ABD1D75F6C282A9A2">リアルタイムレポート </li> 
     <li id="li_3797DF9C40D1426588819116362962F5">Analysis Workspace アクセス </li> 
    </ul> <p>定義済みのグループで以前に使用可能だったすべての設定がユーザーグループの定義の「<span class="wintitle">レポートアクセス</span>」設定</a>でカスタマイズに利用できるので、管理者は、カスタムグループを削除して、独自のものを作成できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディメンションレベルの権限 </p> </td> 
   <td colname="col2"> <p>権限をカスタマイズして、（指標に加えて）ディメンションへのアクセス権を含めたり、除外したりできます。 </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>カスタムグループ内にあるすべてのディメンションと指標は新しいカテゴリに自動的に移行されます。既存のグループで指標が有効な場合、新しく権限を付与できるすべてのディメンション（eVar およびコンテンツに対応するもの）および指標は、デフォルトで有効になります。 </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> 分類インポーター（以前の SAINT）の権限：分類へのアクセスは、分類の基となる<a href="https://docs.adobe.com/content/help/ja-JP/analytics/components/classifications/c-classifications.html">変数</a>へのアクセスによって判断されます。 </li> 
    </ul> <p><a href="/help/admin/user-management2/c-customize-report-access/groups-dimensions.md">ディメンションの権限のカスタマイズ</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://helpx.adobe.com/enterprise/using/admin-console.html">Adobe Admin Console</a> </p> </td> 
   <td colname="col2"> <p>新規のお客様または <a href="https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/core-services.html">Experience Cloud でプロビジョニングされた</a>会社を持つお客様の場合にのみお勧めします。既存の <span class="keyword">Analytics</span> のお客様の <span class="keyword">Experience Cloud</span> ID 管理システムへの移行は、予定されています。 </p> <p>詳しくは、<a href="https://docs.adobe.com/content/help/ja-JP/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html">Admin Console への Analytics ユーザーの移行</a>を参照してください。 </p> </td> 
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

