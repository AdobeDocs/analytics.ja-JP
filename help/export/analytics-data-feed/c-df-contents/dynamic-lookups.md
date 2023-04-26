---
title: 動的検索
description: 動的検索とは何か、および動的検索を有効にする方法について説明します。 通信事業者、モバイル属性、オペレーティングシステムタイプが含まれます。
source-git-commit: b6084fc34165ea602fce616e13b3adfcd7bdfdbd
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# 動的検索

動的検索を使用すると、データフィードで追加の参照ファイルを受け取ることができます。このファイルがない場合は、利用できません。 この設定により、各データフィードファイルと共に次のルックアップテーブルを送信できます。

* **通信事業者名**:追加のコンテキストを提供します。 `carrier` 列。 含まれるファイル名は `carrier.tsv`.
* **モバイル属性**:追加のコンテキストを提供します。 `mobile_id` 」列に追加されます。この列には、各モバイルデバイスで追跡されるすべての機能が含まれます。 含まれるファイル名は `mobile_attributes.tsv`.
* **オペレーティングシステムの種類**:の代替コンテキストを提供します。 `os` 列。 両方 `operating_systems.tsv` および `operating_system_type.tsv` を使用します。 `os` 列をキーとして使用しますが、 `operating_system_type.tsv` は動的検索です。

## 動的検索を有効にする

前述の参照ファイルを受け取る場合は、次の前提条件をすべて満たす必要があります。

* キー列は、データフィードに含める必要があります。
   * の場合 `carrier.tsv`を含める必要があります。 `carrier`.
   * の場合 `mobile_attributes.tsv`を含める必要があります。 `mobile_id`.
   * の場合 `operating_system_type.tsv`を含める必要があります。 `os`.
* 次の列を **除外済み**. これらの列のいずれかがデータフィードに含まれている場合、追加のルックアップテーブルは含まれません。
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

データフィードが列の追加要件と除外要件を満たしたら、データフィード ID をサポートに連絡し、動的な検索を有効にするようリクエストします。

## 参照ヘッダーの参照

これらの参照ファイルの列ヘッダーは、時間の経過と共に変化しないので、各データフィードファイルにはヘッダーが含まれません。 これらの列ヘッダーを参照として使用するか、それぞれのヘッダーをダウンロードします `.tsv` ファイル。

+++**通信事業者名**
ダウンロード [carrier_headers.tsv](assets/carrier_headers.tsv) または以下のヘッダーを参照します。

`carrier`
`Carrier Name`
+++

+++**モバイル属性**
ダウンロード [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) または以下のヘッダーを参照します。

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**オペレーティングシステムの種類**
ダウンロード [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) または以下のヘッダーを参照します。

`os`
`Operating System Type`
+++