---
description: Analytics レポート API の比較表です。サポートドキュメントへのリンクが設定されています。
seo-description: Analytics レポート API の比較表です。サポートドキュメントへのリンクが設定されています。
seo-title: Analytics レポート API の比較
solution: Analytics
title: Analytics レポート API の比較
uuid: fa533a8e-33c0-42f4- a294- cabee0258c8f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Analytics レポート API の比較

Analytics レポート API の比較表です。サポートドキュメントへのリンクが設定されています。

>[!NOTE]
>
>遅延について、Analytics for Target（A4T）は、統合レポート用に同じヒットのAnalyticsデータとTargetデータを組み合わせます。Analytics と Target の呼び出しは、異なる時間に発生するので、両方のソリューションからデータを収集するために、ヒットは、処理が発生する前に格納されます。この処理により、すべてのチェックポイントに&#x200B;**さらに 7 ～ 10 分**&#x200B;の遅延が追加されます。

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API のタイプ </th> 
   <th colname="col2" class="entry"> 完全処理済み </th> 
   <th colname="col3" class="entry"> リアルタイム </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>説明</b> </td> 
   <td colname="col2"> Analytics インターフェイスで利用できる、完全に処理済みで、ファイナライズされたデータ。 </td> 
   <td colname="col3"> 数秒間の収集で部分的に処理された、制限された指標。 </td> 
   <td colname="col4"> 数秒間の収集で部分的に処理されたヒットデータ。 </td> 
   <td colname="col5"> 大量のデータエクスポートを引き出すために使用される、完全に処理済みで、ファイナライズされたデータ。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf" format="https" scope="external"> 遅延</a> </p> </td> 
   <td colname="col2"> 30 ～ 90 分 </td> 
   <td colname="col3"> * 数秒 ～ 10 分 </td> 
   <td colname="col4"> 数秒 ～ 10 分 </td> 
   <td colname="col5"> 90 分以上 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理の完了</b> </td> 
   <td colname="col2"> フル </td> 
   <td colname="col3"> 部分的 </td> 
   <td colname="col4"> 部分的 </td> 
   <td colname="col5"> フル </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/" format="https" scope="external"> レポートインターフェイス</a> </td> 
   <td colname="col2"> Reports &amp; Analytics、Report Builder、API </td> 
   <td colname="col3"> Reports &amp; Analytics、Report Builder、API のリアルタイムレポート </td> 
   <td colname="col4"> API のみ </td> 
   <td colname="col5"> Data Warehouse および API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>データの精度</b> </td> 
   <td colname="col2"> 集計済み </td> 
   <td colname="col3"> 集計済み </td> 
   <td colname="col4"> ヒットレベル </td> 
   <td colname="col5"> 集計済み </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>訪問者プロファイルの処理</b> </td> 
   <td colname="col2"> ○ </td> 
   <td colname="col3"> × </td> 
   <td colname="col4"> × </td> 
   <td colname="col5"> ○ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>サポートセグメント</b> </td> 
   <td colname="col2"> ○ </td> 
   <td colname="col3"> × </td> 
   <td colname="col4"> × </td> 
   <td colname="col5"> はい（ただし、Data Warehouse 互換セグメントのみ） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> Standard+ </td> 
   <td colname="col3"> Standard+ </td> 
   <td colname="col4"> Premium Complete または Predictive Intelligence </td> 
   <td colname="col5"> Standard+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ドキュメント</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B" format="https" scope="external"> Web サービス</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time" format="https" scope="external"> リアルタイムレポート</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B" format="https" scope="external"> Livestream の概要</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html" format="https" scope="external"> Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**関連するヘルプ**

* [Adobe I/O](https://www.adobe.io/) - アドビのテクノロジーをアプリケーションに統合するために必要な技術ドキュメントおよびツールの包括的なソース。
* [Data Workbench Query API](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

