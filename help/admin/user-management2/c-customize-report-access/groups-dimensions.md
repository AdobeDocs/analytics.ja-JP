---
description: eVar、トラフィックレポート、ソリューションレポートおよびパスレポートを含む、詳細なレベルでユーザーアクセスをカスタマイズします。
keywords: グループ;権限
subtopic: Users and groups
title: ディメンションの権限のカスタマイズ
feature: 管理ツール
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
exl-id: 51c4193a-426e-46a0-8494-163b58588157
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 98%

---

# ディメンションの権限のカスタマイズ

>[!IMPORTANT]
>
>ユーザーおよび製品管理は、[Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移行されます。ユーザーを移行する時期は、アドビから通知されます。すべての顧客が移行されたら、**[!UICONTROL Analytics]**／**[!UICONTROL 管理ツール]**／**[!UICONTROL ユーザー管理]**&#x200B;のヘルプコンテンツは利用できなくなります。

eVar、トラフィックレポート、ソリューションレポートおよびパスレポートを含む、詳細なレベルでユーザーアクセスをカスタマイズします。

**[!UICONTROL ユーザー管理]**／**[!UICONTROL グループ]**／**[!UICONTROL レポートアクセス]**／**[!UICONTROL ディメンション]**／**[!UICONTROL カスタマイズ]**

>[!IMPORTANT]
>
>一部のディメンションについては、現時点では権限を指定できません。このようなディメンションとしては、モバイルのブックマークの長さ、モバイルデバイス番号、モバイル DRM、モバイル情報サービス、モバイル Java VM、モバイルデコレーションメール、モバイルインターネットプロトコル、モバイル OS、モバイルプッシュトゥトークがあります。
>
>これらのディメンションは、他の権限にかかわらず、すべてのユーザーが使用可能です。

このページの設定は、[!UICONTROL ユーザーグループの定義]ページで選択されたレポートスイートに関係します。

![](assets/permissions-dimensions.png)

権限のディメンションカテゴリに関する次の情報について説明します。

* eVar 1 ～250 に対して個別に権限が与えられます。
* すべてのトラフィックレポートはディメンションです。
* ビデオおよびモバイルレポートおよびその他の Analytics ソリューリョンレポート（Experience Manager、Advertising Cloud、Social など）はディメンションです。
* パスレポートは、ユーザーが親ディメンションにアクセスできる場合に使用できます。
* カスタムグループ内にあるすべてのディメンションと指標は新しいカテゴリに自動的に移行されます。既存のグループで指標が有効な場合、新しく権限を付与できるすべてのディメンション（eVar およびコンテンツに対応するもの）および指標は、デフォルトで有効になります。
* 分類インポーター（以前の SAINT）の権限：分類へのアクセスは、分類の基となる[変数](https://docs.adobe.com/content/help/ja-JP/analytics/components/classifications/c-classifications.html)へのアクセスによって判断されます。

詳しくは、[ユーザーとグループの権限の変更](https://docs.adobe.com/content/help/ja-JP/analytics/admin/user-product-management/user-management/permissions-changes.html)を参照してください。

**ディメンションのカスタマイズ**

次の項目は、権限を設定できるディメンションです。

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
   <td colname="col2"> <p>eVar 1 ～250 に対して個別に権限が与えられます。eVar は、カスタムレポートのコンバージョン成功指標をセグメント化するために使用するカスタムコンバージョン変数です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/implementation/vars/page-vars/evar.html"> prop </a> </p> </td> 
   <td colname="col2"> <p>prop は、カスタムトラフィック変数です。 </p> <p>Analytics の導入の<a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/evar.html">トラフィック prop と コンバージョン eVar</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/implementation/vars/page-vars/page-variables.html"> 階層 </a> </p> </td> 
   <td colname="col2"> <p> 階層（hierN）変数は、サイトの階層またはページ構造におけるページの位置を決定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> リスト Prop の機能と同様、リスト変数は、同じイメージリクエスト内で複数の値を許可します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Analytics の標準（標準搭載の）Analytics のディメンション。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/jp/support/experience-manager.html"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/jp/support/advertising-cloud.html"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/analyze/activity-map/activity-map.html"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Activity Map レポートディメンション：Activity Map ページ、Activity Map リンク、Activity Map 地域、Activity Map 地域別リンク、Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/ja-JP/media-analytics/using/media-overview.html"> モバイル </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>このパートナーとの統合は無効になりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>このパートナーとの統合は無効になりました。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>未使用。 </p> </td> 
  </tr> 
 </tbody> 
</table>
