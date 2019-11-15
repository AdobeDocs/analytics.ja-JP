---
description: フィードを設定する際に、ジョブの頻度を決定するいくつかの設定が処理されます。
keywords: Data Feed;job;settings;daily;hourly;Data Backfills for Hourly Data Feeds;backfill
solution: Analytics
title: ジョブ設定
uuid: e124b4f1-0168-4eaa-8657-19207b2f263f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# ジョブ設定

フィードを設定する際に、ジョブの処理頻度を決定する設定が一部あります。

次の設定を使用して、ジョブの処理時間を設定します。これらの設定は、ジョブレベルではなく、フィードレベルで設定されます。

<table id="table_2070F73212F245E98DADC6B5DFDB1C72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 毎日 </td> 
   <td colname="col2"> <p>毎日のデータは、単一の zip ファイルで配信されます。このファイルのサイズは、2 GB までに制限されます。ファイルが 2 GB の非圧縮データを超えると、追加のファイルが作成されます。毎日 1 回、すべてのファイルが含まれる配信を受け取ります。 </p> <p>各ファイルは、次の形式で名前が付けられています。 </p> <p> <span class="filepath"> <span class="varname"> reportsuite</span>-<span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 毎時（デフォルト） </td> 
   <td colname="col2"> <p>毎時のデータが、その時間に受け取ったすべてのデータを含む 1 つの圧縮ファイルで配信されます。毎日 24 回の配信を受け取ります。各ファイルはその 1 時間のデータが処理された後に配信されます。 </p> <p>「時間別」という用語は、配信が発生する時間枠ではなく、個々のデータエクスポートで送信されるデータの時間枠を表します。 時間別データフィードはベストエフォート方式で処理および配信されます。 </p> <p>時間別データフィードの場合、95%の割合で、その時間分のデータの終了から12時間以内に配信が行われることを期待しています。 大量のトラフィックのあるレポートスイートのデータフィードは、処理および配信により多くの時間がかかる可能性があります。 </p> <p>時間別データフィードの受信は、日別データフィードを複数ファイルで受信することとは異なります。時間別データフィードを受信する場合、1 日のデータはそれぞれ 1 時間分の収集データごとに 24 個のファイルに分割され、各ファイルが準備でき次第配信されます。日別データフィードを複数ファイルで受信する場合、配信は 1 日 1 回、前日のデータの処理後に行われ、ファイルは収集データの分量に応じて 2GB 単位に分割されます。 </p> <p>各ファイルは、次の形式で名前が付けられています。 </p> <p> <span class="filepath"> <span class="varname"> reportsuite</span>-<span class="varname"> date</span>-<span class="varname"> hour</span>.tar</span> </p> <p>毎時のフィードに影響する可能性のある要因について詳しくは、<a href="/help/export/analytics-data-feed/c-df-contents/jobs-faq.md"  >ジョブの FAQ</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間別データフィードのためのデータバックフィル </td> 
   <td colname="col2"> <p>新しく時間別データフィードが設定されたタイミングよりも早い日付のデータをリクエストする場合、60 日以上前の日付のデータが、時間別でなく日別の形式で配信されることがあります。 </p> <p>この場合、それらの日付については 24 通個別に配信されず、代わりに、それらの日付のすべてのデータを含むタイムスタンプが真夜中の配信 1 通を受け取ります。この種のバックフィルをリクエストする場合は、ETL が日別の配信を処理するように設定されていることを確認してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

