---
title: 動的検索
description: 動的検索の概要と有効化方法について説明します。 通信事業者、モバイル属性、オペレーティングシステムの種類が含まれます。
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# 動的検索

動的検索を使用すると、追加の参照ファイルをデータフィードで受け取ることができます。それ以外の場合は使用できません。 この設定では、各データフィードファイルで次のルックアップテーブルを送信できます。

* **通信事業者名**：の追加コンテキストを提供します `carrier` 列。 含まれるファイル名は次のとおりです `carrier.tsv`.
* **モバイル属性**：の追加コンテキストを提供します `mobile_id` 列（各モバイルデバイスで追跡されたすべての機能を含む）。 含まれるファイル名は次のとおりです `mobile_attributes.tsv`.
* **オペレーティングシステムの種類**：の代替コンテキストを提供します `os` 列。 両方 `operating_systems.tsv` および `operating_system_type.tsv` を使用する `os` 列がキーになっていますが、のみ `operating_system_type.tsv` は動的検索です。

## 動的検索の有効化

前述の参照ファイルを受け取るには、次の前提条件をすべて満たす必要があります。

* キー列をデータフィードに含める必要があります。
   * の場合 `carrier.tsv`を含める必要があります `carrier`.
   * の場合 `mobile_attributes.tsv`を含める必要があります `mobile_id`.
   * の場合 `operating_system_type.tsv`を含める必要があります `os`.
* 次の列は、である必要があります **除外済み**. データフィードにこれらの列が含まれている場合は、 `mobile_attributes.tsv` 動的検索は含まれません。
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

データフィードが列の包含および除外の要件を満たしたら、カスタマーケアにデータフィード ID を連絡し、動的検索を有効にするようリクエストします。

## 参照ヘッダーの参照

これらの参照ファイルの列ヘッダーは、時間の経過に伴って変化しないので、各データフィードファイルにはヘッダーは含まれません。 これらの列ヘッダーを参照として使用するか、それぞれダウンロードします `.tsv` ファイル。

+++**通信事業者名**
Download [carrier_headers.tsv](assets/carrier_headers.tsv) または、以下のヘッダーを参照してください。

`carrier`
`Carrier Name`
+++

+++**モバイル属性**
Download [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) または、以下のヘッダーを参照してください。

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
Download [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) または、以下のヘッダーを参照してください。

`os`
`Operating System Type`
+++
