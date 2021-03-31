---
description: Analytics レポート API の比較表です。サポートドキュメントへのリンクが設定されています。
title: Analytics レポート API の比較
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
feature: API
role: 開発者
translation-type: tm+mt
source-git-commit: 4359f451692b86087efe27d4b3ec49ca85b7addc
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 100%

---


# Analytics レポート API の比較

Analytics レポート API の比較表です。サポートドキュメントへのリンクが設定されています。

>[!NOTE]
>
> 遅延に関して、Analytics for Target（A4T）は、統合レポートのために、同じヒットの Analytics と Target のデータを組み合わせます。Analytics と Target の呼び出しは、異なる時間に発生するので、両方のソリューションからデータを収集するために、ヒットは、処理が発生する前に格納されます。この処理により、すべてのチェックポイントに&#x200B;**さらに 7 ～ 10 分**&#x200B;の遅延が追加されます。

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
   <td colname="col1"> <p><a href="https://docs.adobe.com/content/help/ja-JP/analytics/technotes/latency.html"  > 遅延</a> </p> </td> 
   <td colname="col2"> 30 ～ 90 分 </td> 
   <td colname="col3"> * 数秒 ～ 10 分 </td> 
   <td colname="col4"> 数秒 ～ 10 分 </td> 
   <td colname="col5"> 90 分 + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理の完了</b> </td> 
   <td colname="col2"> フル </td> 
   <td colname="col3"> 部分的 </td> 
   <td colname="col4"> 部分的 </td> 
   <td colname="col5"> フル </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://docs.adobe.com/content/help/ja-JP/analytics/landing/home.html"  > レポートインターフェイス</a> </td> 
   <td colname="col2"> Analysis Workspace、Reports &amp; Analytics、Report Builder、API </td> 
   <td colname="col3"> Reports &amp; Analytics、Report Builder、1.4 API のリアルタイムレポート </td> 
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
   <td colname="col1"> <b>ドキュメント</b> </td> 
   <td colname="col2"> <p> <a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html"  > Analytics API</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis"  > リアルタイムレポート</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md"  > Livestream の概要</a> </p> </td> 
   <td colname="col5"> <p><a href="https://docs.adobe.com/content/help/ja-JP/analytics/export/data-warehouse/data-warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**関連するヘルプ**

* [Adobe/IO](https://www.adobe.io/) - アドビのテクノロジーをアプリケーションに統合するために必要な技術ドキュメントおよびツールの包括的なソース。
* [Data Workbench Query API](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

