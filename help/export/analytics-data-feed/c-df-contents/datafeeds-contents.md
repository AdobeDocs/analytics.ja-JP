---
description: このセクションでは、データフィード配信に含まれるファイルについて説明します。
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
subtopic: data feeds
title: データフィードの内容 - 概要
topic: Reports and analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# データフィードの内容 - 概要

このセクションでは、データフィード配信に含まれるファイルについて説明します。

## マニフェストファイル

マニフェストファイルには、アップロードされるデータセット内の各ファイルに関する以下の詳細情報が含まれます。

* File name
* ファイルサイズ
* MD5 ハッシュ
* ファイルに含まれるレコードの数

マニフェストファイルは、Java JAR マニフェストファイルと同じ書式に従います。

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. マニフェストファイルには以下の書式の名前が付けられます。

```text
[rsid]_[YYYY-mm-dd].txt
```

一般的なマニフェストファイルには以下のようなデータが含まれています。

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

すべてのマニフェストファイルに、参照ファイルの合計数、データファイルの合計数、全データファイル内のレコードの合計数を示すヘッダーが含まれています。このヘッダーの後に、データフィード配信に含まれる各ファイルの情報が記述された複数のセクションが続きます。

Some feeds are configured to receive a `.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## 参照ファイル

一部のデータフィード列は、実際の値に対応する数値を出力します。 ルックアップファイルは、データフィード列の数値を照合し、実際の値と照合するために使用されます。 例えば、「ヒットデータ」列の値が「497」の場合、「Microsoft Internet Explorer 8」からのヒットであることを示します（を参照） `browser``browser.tsv`。

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. それ以外のファイル（`browser.tsv` など）は汎用ファイルです。

参照ファイルは次の書式の名前を持つ 1 つのファイルに圧縮されて配信されます。

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
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

## ヒットデータファイル

Hit data is provided in a [!DNL hit_data.tsv] file. このファイルに含まれるデータの分量は、配信形式（時間別または日別、および単一ファイルまたは複数ファイル）によって異なります。このファイルにはヒットデータのみが含まれます。列ヘッダーは、参照ファイルと一緒に別途配信されます。このファイル内の各行には 1 個のサーバーコールが含まれます。

アドビから配信されるファイルは、設定したデータフィードの種類によって異なります。 すべてのファイルはISO-8859-1を使用してエンコードされます。

* `[rsid]` は、データフィードの元となるレポートスイートIDを指します。
* `[index]` は、複数のファイルフィードでのみ使用され、ページ分割されたファイルの正しい順序を示します。
* `[YYYY-mm-dd]` は、データフィードの開始日を指します。
* `[HHMMSS]` は時間別フィードでのみ使用され、データフィードの開始時間を示します。
* `[compression_suffix]` は、使用される圧縮のタイプを指します。 通常、データフィードはファイルに圧 `tar.gz` 縮さ `zip` れます。

### 日別、単一ファイル

1日分のデータが収集された後、圧縮された1つのデータファイルとマニフェストファイルを受け取ります。 データファイルの名前は次のとおりです。

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

抽出すると、その日のすべてのデータを含む1つの `hit_data.tsv` ファイルと、必要な列の参照ファイルがデータファイルに格納されます。

### 毎日、複数のファイル

1日分のデータが収集された後、1つ以上の圧縮データファイルとマニフェストファイルを受け取ります。 データファイルの名前は次のとおりです。

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

抽出すると、各データファイルには約2 GBの非圧縮 `hit_data.tsv` データと、必要な列の参照ファイルが含まれる1つのファイルが含まれます。

### 時間別、単一ファイル

1時間分のデータが収集された後、1つの圧縮データファイルとマニフェストファイルを受け取ります。 データファイルの名前は次のとおりです。

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

抽出すると、データファイルには、その時間のすべてのデ `hit_data.tsv` ータを含む単一のファイルと、必要な列の参照ファイルが含まれます。

### 時間別、複数ファイル

1時間分のデータが収集された後、1つ以上の圧縮データファイルとマニフェストファイルを受け取ります。 データファイルの名前は次のとおりです。

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

抽出すると、各データファイルには約2 GBの非圧縮 `hit_data.tsv` データと、必要な列の参照ファイルが含まれる1つのファイルが含まれます。

## データファイルサイズ

ヒットデータのファイルサイズは、アクティブに使用される変数の数や、レポートスイートに送信されるトラフィックの量に応じて大きく異なります。 ただし、データ 1 行の平均は約 500 B（圧縮時）または 2 KB（非圧縮時）です。これにサーバーコールの数を掛けると、データフィードファイルの大きさに関する概算値が得られます。 組織がデータフィードファイルの受信を開始すると、行数を合計ファイルサイズで割ることで、より正確な数 `hit_data.tsv` を見つけることができます。
