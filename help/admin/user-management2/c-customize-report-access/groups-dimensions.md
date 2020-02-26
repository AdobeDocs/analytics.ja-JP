---
description: eVar、トラフィックレポート、ソリューションレポートおよびパスレポートを含む、詳細なレベルでユーザーアクセスをカスタマイズします。
keywords: groups;permissions
subtopic: Users and groups
title: ディメンションの権限のカスタマイズ
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# ディメンションの権限のカスタマイズ

> [!IMPORTANT]ユーザーおよび製品管理は、[Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移行されます。ユーザーを移行する時期は、アドビから通知されます。すべての顧客が移行されたら、**[!UICONTROL Analytics]**／**[!UICONTROL 管理ツール]**／**[!UICONTROL ユーザー管理]**&#x200B;のヘルプコンテンツは利用できなくなります。

eVar、トラフィックレポート、ソリューションレポートおよびパスレポートを含む、詳細なレベルでユーザーアクセスをカスタマイズします。

**[!UICONTROL ユーザー管理]**／**[!UICONTROL グループ]**／**[!UICONTROL レポートアクセス]**／**[!UICONTROL ディメンション]**／**[!UICONTROL カスタマイズ]**

> [!IMPORTANT]一部のディメンションについては、現時点では権限を指定できません。このようなディメンションとしては、モバイルのブックマークの長さ、モバイルデバイス番号、モバイル DRM、モバイル情報サービス、モバイル Java VM、モバイルデコレーションメール、モバイルインターネットプロトコル、モバイル OS、モバイルプッシュトゥトークがあります。
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
* 分類インポーター（以前の SAINT）の権限：分類へのアクセスは、分類の基となる[変数](https://marketing.adobe.com/resources/help/ja_JP/reference/c_classifications.html)へのアクセスによって判断されます。

詳しくは、[権限の変更に関するよくある質問](https://marketing.adobe.com/resources/help/ja_JP/reference/permissions_faq.html)を参照してください。

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
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/sc/implement/props_eVars.html"> prop </a> </p> </td> 
   <td colname="col2"> <p>prop は、カスタムトラフィック変数です。 </p> <p>Analytics の導入の<a href="https://marketing.adobe.com/resources/help/ja_JP/sc/implement/props_eVars.html">トラフィック prop と コンバージョン eVar</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/sc/implement/hierN.html"> 階層 </a> </p> </td> 
   <td colname="col2"> <p> 階層（hierN）変数は、サイトの階層またはページ構造におけるページの位置を決定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/ja_JP/sc/implement/listN.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> リスト Prop の機能と同様、リスト変数は、同じイメージリクエスト内で複数の値を許可します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Analytics の標準（標準搭載の）Analytics のディメンション。 </p> </td> 
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
