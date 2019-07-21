---
description: このセクションでは、データフィード配信に含まれるファイルについて説明します。
keywords: データフィード;job;content;manifest;file;参照;ヒットデータ、配信コンテンツ
seo-description: このセクションでは、データフィード配信に含まれるファイルについて説明します。
seo-title: データフィードの内容-概要
solution: Analytics
subtopic: データフィード
title: データフィードの内容-概要
topic: Reports and Analytics
uuid: 82a86314-4841-4133- a0dc-4e7c6cd14fc1
translation-type: tm+mt
source-git-commit: 7fe23291d8ee9675181065025692108aee3ea9a5

---


# データフィードの内容-概要

このセクションでは、データフィード配信に含まれるファイルについて説明します。

## マニフェストファイル {#section_044BBDE2906D49518F8264CD4832D429}

マニフェストファイルには、アップロードされるデータセット内の各ファイルに関する以下の詳細情報が含まれます。

* ファイル名
* ファイルサイズ
* MD5 ハッシュ
* ファイルに含まれるレコードの数

マニフェストファイルは、Java JAR マニフェストファイルと同じ書式に従います。

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. マニフェストファイルには以下の書式の名前が付けられます。

```
<report_suite_id>_YYYY_MM_DD.txt
```

一般的なマニフェストファイルには以下のようなデータが含まれています。

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: bugzilla_2012-09-09-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-bugzilla_2012-09-09.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

すべてのマニフェストファイルに、参照ファイルの合計数、データファイルの合計数、全データファイル内のレコードの合計数を示すヘッダーが含まれています。このヘッダーの後に、データフィード配信に含まれる各ファイルの情報が記述された複数のセクションが続きます。

Some feeds are configured to receive a `rsid_YYYY-MM-DD.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## 参照ファイル {#section_B5863537A48D47D78D0F7274838923C1}

参照ファイルにはヒットデータは含まれません。参照ファイルは、ヒットデータの列ヘッダーを提供する補助ファイル、およびデータフィード内の ID を実際の値に変換するための参照ファイルです。例えば、ブラウザー列の値「497」は、そのヒットが「Microsoft Internet Explorer 8」からのものであることを示します。

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. それ以外のファイル（`browser.tsv` など）は汎用ファイルです。

参照ファイルは次の書式の名前を持つ 1 つのファイルに圧縮されて配信されます。

```
<report_suite_id>_<YYYY-mm-dd>-<HHMMSS>-lookup_data.<compression_suffix>
```

* [!DNL column_headers.tsv]（このデータフィード用にカスタマイズされています）
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv]（このデータフィード用にカスタマイズされています）

## ヒットデータファイル {#section_B0745236104E41F2BA625D24AB442636}

Hit data is provided in a [!DNL hit_data.tsv] file. このファイルに含まれるデータの分量は、配信形式（時間別または日別、および単一ファイルまたは複数ファイル）によって異なります。このファイルにはヒットデータのみが含まれます。列ヘッダーは、参照ファイルと一緒に別途配信されます。このファイル内の各行には 1 個のサーバーコールが含まれます。

## 配信内容 {#section_994B43D1E71A4EFDB2E4183C0929A397}

>[!NOTE]
>
>ファイルはISO-8859-1を使用してエンコードされます。

アドビから配信される実際のファイルは、設定したデータフィードの種類によって異なります。使用するデータフィードと一致する設定については、以下の表の配信ファイルの説明を参照してください。

ファイル名で示される時刻（HHMMSS）は、ファイルの作成時またはアップロード時の時刻とは関係なく、常にファイル内のデータの日時範囲の開始時刻を示します。

<table id="table_DBF34F39D29D4DA2B2689029CDA24B92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 配信形式 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 日別、単一ファイル </td> 
   <td colname="col2"> <p>1 日分のデータが収集された後、以下の内容が配信されます。 </p> 
    <ul id="ul_D630D73D0DBA440FA704CF31856243C7"> 
     <li id="li_717873DBBF264422A39217E1A8829742">単一の圧縮データファイル。 </li> 
     <li id="li_9F75D42FD56E4CC89C4683D32E59337B">マニフェストファイル。 </li> 
    </ul> <p>データファイルは以下のような書式の名前で配信されます。 </p> 
    <code>&lt; report_ suite&gt;_&lt; YYYY- mm- dd&gt;.&lt;compression_suffix&gt;
    </code> <p> <code>&lt;compression_suffix&gt;</code> の部分は <code>tar.gz</code> または <code>zip</code> です。 </p> <p>圧縮解除すると、データファイルには、その日の全データが含まれる 1 つの <span class="filepath">hit_data.tsv</span> ファイルと、前述の圧縮参照ファイルが含まれています。 </p> <p>ヒットデータのファイルサイズは、レポートスイートでアクティブに使用される変数の数およびトラフィック量に応じて大きく異なります。ただし、データ 1 行の平均は約 500 B（圧縮時）または 2 KB（非圧縮時）です。これにサーバーコールの数をかけることによって、データフィードファイルのおおよその大きさを概算できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日別、複数ファイル </td> 
   <td colname="col2"> <p>1 日分のデータが収集された後、以下の内容が配信されます。 </p> 
    <ul id="ul_4B873D3F6F18467890C36AE8E86F49DA"> 
     <li id="li_227315384B954A5784FA370D9B30E2AF">1 個または複数の圧縮データファイル。2 GB ごとのチャンクに分割されています。 </li> 
     <li id="li_4169D889CEA3446CB5FAA08FD60AA0D0">マニフェストファイル。 </li> 
    </ul> <p>各データファイルは以下のような書式の名前で配信されます。 </p> 
    <code>&lt; index&gt;-&lt; report_ suite&gt;_&lt; YYYY- mm- dd&gt;.&lt;compression_suffix&gt;
    </code> <p> <code>&lt;index&gt;</code> の部分はファイル数 <i>n</i> 個の場合に <i>1</i> から <i>n</i> まで順に大きくなるファイルインデックス、<code>&lt;compression_suffix&gt;</code> の部分は <code>tar.gz</code> または <code>zip</code> です。 </p> <p>圧縮解除すると、各データファイルには約 2 GB の非圧縮データが含まれる 1 つの <span class="filepath">hit_data.tsv</span> ファイルと、前述の圧縮参照ファイルが含まれています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間別、単一ファイル </td> 
   <td colname="col2"> <p>1 時間分のデータが収集された後、以下の内容が配信されます。 </p> 
    <ul id="ul_29B06981A4F74D2AA1171D733C5FB1F4"> 
     <li id="li_072BBC4BA9B84C61B4E8EFA35F54707B">単一のデータファイル。 </li> 
     <li id="li_E2D05E9DAE814309B6BC91798BB29FBB">マニフェストファイル。 </li> 
    </ul> <p>データファイルは以下のような書式の名前で配信されます。 </p> 
    <code>&lt; report_ suite&gt;_&lt; YYYY- mm- dd&gt;-&lt; HHMMSS&gt;.&lt;compression_suffix&gt;
    </code> <p> <code>&lt;compression_suffix&gt;</code> の部分は <code>tar.gz</code> または <code>zip</code> です。 </p> <p>圧縮解除すると、データファイルには、その 1 時間の全データが含まれる 1 つの <span class="filepath">hit_data.tsv</span> ファイルが含まれています。その日の最初の 1 時間のデータの場合のみ、前述の圧縮参照ファイルが一緒に配信されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間別、複数ファイル </td> 
   <td colname="col2"> <p>1 時間分のデータが収集された後、以下の内容が配信されます。 </p> 
    <ul id="ul_A739BA12B66547A28BA45E0B9B747B16"> 
     <li id="li_C0DF059D1E6843C8A38E24CA1B59D99C">1 個または複数の圧縮データファイル。2 GB ごとのチャンクに分割されています。 </li> 
     <li id="li_604266DA9B8A4000905C44C95DA65D14">マニフェストファイル。 </li> 
    </ul> <p>各データファイルは以下のような書式の名前で配信されます。 </p> 
    <code>&lt; index&gt;-&lt; report_ suite&gt;_&lt; YYYY- mm- dd&gt;-&lt; HHMMSS&gt;. tsv.&lt;compression_suffix&gt;
    </code> <p><code>&lt;index&gt;</code> の部分はファイル数 <i>n</i> 個の場合に <i>1</i> から <i>n</i> まで順に大きくなるファイルインデックス、<code>&lt;compression_suffix&gt;</code> の部分は <code>gz</code> または <code>zip</code> です。 </p> <p>圧縮解除すると、各データファイルには約 2 GB の非圧縮データが含まれる 1 つの <span class="filepath">hit_data.tsv</span> ファイルが含まれています。その日の最初の 1 時間のデータの場合のみ、前述の圧縮参照ファイルが一緒に配信されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

