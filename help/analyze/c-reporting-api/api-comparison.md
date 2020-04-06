---
description: AnalyticsレポートAPIの比較表。 サポートするドキュメントへのリンクが提供されます。
title: Analytics レポート API の比較
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analytics レポート API の比較

AnalyticsレポートAPIの比較表。 サポートするドキュメントへのリンクが提供されます。

>[!NOTE] 遅延に関して、Analytics for Target（A4T）は、統合レポートのために、同じヒットの Analytics と Target のデータを組み合わせます。Analyticsとターゲット呼び出しは異なる時間に発生するので、両方のソリューションからデータを収集するために、ヒットは処理が発生する前に保存されます。 この処理により、 **すべてのチェックポイントに** 7 ～ 10分の待ち時間が追加されます。

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> APIタイプ </th> 
   <th colname="col2" class="entry"> 処理済み </th> 
   <th colname="col3" class="entry"> リアルタイム </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>説明</b> </td> 
   <td colname="col2"> すべてのAnalyticsインターフェイスで使用できる、完全に処理され、ファイナライズされたデータ。 </td> 
   <td colname="col3"> 数秒間の収集で部分的に処理され、制限された指標を使用できます。 </td> 
   <td colname="col4"> 数秒間の収集で部分的に処理されたヒットデータ。 </td> 
   <td colname="col5"> 大量のデータエクスポートの取り込みに使用される、完全に処理された、ファイナライズされたデータ。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf"  > 遅延</a> </p> </td> 
   <td colname="col2"> 30 ～ 90分 </td> 
   <td colname="col3"> *秒～ 10分 </td> 
   <td colname="col4"> 数秒～ 10分 </td> 
   <td colname="col5"> 90 分 + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理の完了</b> </td> 
   <td colname="col2"> フル </td> 
   <td colname="col3"> 部分 </td> 
   <td colname="col4"> 部分 </td> 
   <td colname="col5"> フル </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/ja_JP/reference/"  > レポートインターフェイス</a> </td> 
   <td colname="col2"> Reports &amp; Analytics、Report Builder、API </td> 
   <td colname="col3"> Reports &amp; Analytics、Report Builder、APIのリアルタイムレポート </td> 
   <td colname="col4"> APIのみ </td> 
   <td colname="col5"> Data WarehouseおよびAPI </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>データ精度</b> </td> 
   <td colname="col2"> 要約済み </td> 
   <td colname="col3"> 要約済み </td> 
   <td colname="col4"> ヒットレベル </td> 
   <td colname="col5"> 要約済み </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>訪問者プロファイル処理</b> </td> 
   <td colname="col2"> ○ </td> 
   <td colname="col3"> × </td> 
   <td colname="col4"> × </td> 
   <td colname="col5"> ○ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>セグメントのサポート</b> </td> 
   <td colname="col2"> ○ </td> 
   <td colname="col3"> × </td> 
   <td colname="col4"> × </td> 
   <td colname="col5"> はい（ただし、Data Warehouseと互換性のあるセグメントのみ） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Analytics SKU</b> </td> 
   <td colname="col2"> 標準+ </td> 
   <td colname="col3"> 標準+ </td> 
   <td colname="col4"> Premium CompleteまたはPredictive Intelligence </td> 
   <td colname="col5"> 標準+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ドキュメント</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > Web サービス</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > リアルタイムレポート</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > Livestream の概要</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/ja_JP/reference/data_warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**関連するヘルプ**

* [Adobe/I/O](https://www.adobe.io/) — アドビのテクノロジーをアプリケーションに統合するために必要な技術ドキュメントとツールの包括的なソースです。
* [Data WorkbenchクエリAPI](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

