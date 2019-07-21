---
description: Activity Map またはレガシー ClickMap でリンクトラッキングを開始する手順です。
seo-description: Activity Map またはレガシー ClickMap でリンクトラッキングを開始する手順です。
seo-title: リンクトラッキングを開始
solution: Analytics
title: リンクトラッキングを開始
topic: Activity Map
uuid: 425cb287- f76e-4430-802f-288499711ba9
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# リンクトラッキングを開始

Activity Map またはレガシー ClickMap でリンクトラッキングを開始する手順です。

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> リンクトラッキングの開始場所... </th> 
   <th colname="col2" class="entry"> 手順... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Appmeasurement.js ファイルから次のコンテンツを追加します。<code>/* START Activity Map MODULEを使用すると、Adobe AnalyticsでActivity Mapトラッキングを有効にできます。Activity Mapを使用すると、ユーザーがWebサイトにどのように関与しているかを把握するために、リンクやコンテンツにデータオーバーレイを表示できます。Activity Mapを使用しない場合は、AppMeasurement. jsファイルから次のコードブロックを削除できます。
  Additional documentation on how to configure Activity Map is available at:
      https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function AppMeasurement_Module_Activity Map(g){func
     ...
     /* END Activity Map MODULE */
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap（旧称 Visitor ClickMap） </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external">trackInlineStats</a> 変数を true に設定します。The syntax reads as follows: 
     <code>
       s.trackInlineStats=true
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

