---
description: eVar、トラフィックレポート、ソリューションレポートおよびパスレポートを含む、詳細なレベルでユーザーアクセスをカスタマイズします。
keywords: groups;permissions
subtopic: Users and groups
title: ディメンションの権限のカスタマイズ
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# ディメンションの権限のカスタマイズ

>[!IMPORTANT]ユーザーおよび製品管理は、[Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移行されます。ユーザーを移行する時期は、アドビから通知されます。After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** will be retired.

eVar、トラフィックレポート、ソリューションレポートおよびパスレポートを含む、詳細なレベルでユーザーアクセスをカスタマイズします。

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Dimensions]** > **[!UICONTROL Customize]**

>[!IMPORTANT]一部のディメンションについては、現時点では権限を指定できません。次のディメンションがあります。モバイルブックマークの長さ；モバイルデバイス番号；Mobile DRM;モバイル情報サービス;Mobile Java VM;Mobile Mail Decoration;モバイルネットプロトコル；Mobile OS;モバイルプッシュトゥトーク。
>
>これらのディメンションは、他の権限に関係なく、すべてのユーザーが使用できます。

このページの設定は、そのページで選択したレポートスイートに関連 [!UICONTROL Define User Groups] します。

![](assets/permissions-dimensions.png)

権限のディメンションカテゴリに関する次の情報を理解します。

* eVar 1 ～ 250に対して個別に権限が付与されます。
* すべてのトラフィックレポートはディメンションです。
* ビデオおよびモバイルレポートおよびその他の Analytics ソリューリョンレポート（Experience Manager、Advertising Cloud、Social など）はディメンションです。
* パスレポートは、親ディメンションにユーザーがアクセスできる場合に使用できます。
* カスタムグループ内の現在のすべてのディメンションと指標は、新しいディメンションに自動的に移行されました。カテゴリ 既存のグループで指標が有効になっている場合、新しく権限を付与可能なすべてのディメンション（eVarおよびコンテンツに応じたディメンション）と指標がデフォルトで提供されます。
* 分類インポーター（以前の SAINT）の権限：分類へのアクセスは、分類の基となる[変数](https://marketing.adobe.com/resources/help/ja_JP/reference/c_classifications.html)へのアクセスによって判断されます。

詳しくは、権限の変更に関す [るよくある質問(FAQ)を参照してください](https://marketing.adobe.com/resources/help/ja_JP/reference/permissions_faq.html)。

**ディメンションのカスタマイズ**

次の項目は、権限を持つディメンションです。

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVar </a> </p> </td> 
   <td colname="col2"> <p>eVar 1 ～ 250に対して個別に権限が付与されます。 eVarは、カスタムレポートでコンバージョン成功指標をセグメント化するために使用するカスタムコンバージョン変数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/sc/implement/props_eVars.html"> prop </a> </p> </td> 
   <td colname="col2"> <p>prop は、カスタムトラフィック変数です。 </p> <p>Analytics の導入の<a href="https://marketing.adobe.com/resources/help/ja_JP/sc/implement/props_eVars.html">トラフィック prop と コンバージョン eVar</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/sc/implement/hierN.html"> 階層 </a> </p> </td> 
   <td colname="col2"> <p> 階層（hierN）変数は、サイトの階層またはページ構造におけるページの位置を決定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/sc/implement/listN.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> リストpropの機能と同様に、リスト変数は同じイメージリクエスト内で複数の値を許可します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準 </p> </td> 
   <td colname="col2"> <p>Analyticsの標準（標準搭載）ディメンションを指します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/em/"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/media-optimizer/"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/analytics/activitymap/"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Activity Map レポートディメンション：Activity Map ページ、Activity Map リンク、Activity Map 地域、Activity Map 地域別リンク、Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/mobile/"> モバイル </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>このパートナーとの統合は無効になりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/ja-JP/media-analytics/using/media-overview.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>このパートナーとの統合は無効になりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>未使用。 </p> </td> 
  </tr> 
 </tbody> 
</table>
