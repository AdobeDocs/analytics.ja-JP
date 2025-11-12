---
title: 動的検索
description: 動的検索の概要と有効化方法について説明します。 通信事業者、モバイル属性、オペレーティングシステムの種類が含まれます。
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
source-git-commit: 705a1716ed0205594fc6c75023c8805024ce7df7
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 2%

---

# 動的検索

動的検索を使用すると、追加の参照ファイルをデータフィードで受け取ることができます。それ以外の場合は使用できません。 この設定では、各データフィードファイルで次のルックアップテーブルを送信できます。

* **通信事業者名**:`carrier` 列の追加コンテキストを提供します。 ファイル名は `carrier.tsv` です。
* **モバイル属性**：各モバイルデバイスで追跡されるすべての機能を含む、`mobile_id` 列の追加コンテキストを提供します。 ファイル名は `mobile_attributes.tsv` です。
* **オペレーティングシステムの種類**:`os` 列の代替コンテキストを提供します。 `operating_systems.tsv` と `operating_system_type.tsv` はどちらも `os` 列をキーとして使用しますが、`operating_system_type.tsv` のみが動的検索です。

## 動的検索の有効化 {#enable-dynamic-lookups}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_dynamic_lookups"
>title="動的検索の有効化"
>abstract="追加のルックアップファイルをデータフィードで受け取る場合は、このオプションを選択します。それ以外の場合、このオプションは使用できません。 この設定では、各データフィードファイルで次のルックアップテーブルを送信できます。<ul><li>通信事業者名</li><li>モバイル属性</li><li>オペレーティングシステムの種類</li></ul>"

<!-- markdownlint-enable MD034 -->

前述の参照ファイルを受け取るには、次の前提条件をすべて満たす必要があります。

* キー列をデータフィードに含める必要があります。
   * `carrier.tsv` の場合、`carrier` を含める必要があります。
   * `mobile_attributes.tsv` の場合、`mobile_id` を含める必要があります。
   * `operating_system_type.tsv` の場合、`os` を含める必要があります。
* 次の列は **除外** する必要があります。 これらの列のいずれかがデータフィードに含まれる場合、`mobile_attributes.tsv` の動的参照は含まれません。
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

データフィードが列の包含および除外の要件を満たしたら、カスタマーケアにデータフィード ID を連絡し、動的検索を有効にするようリクエストします。

## 参照ヘッダーの参照

これらの参照ファイルの列ヘッダーは、時間の経過に伴って変化しないので、各データフィードファイルにはヘッダーは含まれません。 これらの列ヘッダーを参照として使用するか、それぞれの `.tsv` ファイルをダウンロードします。

+++**通信事業者の名称**
[carrier_headers.tsv](assets/carrier_headers.tsv) をダウンロードするか、以下のヘッダーを参照してください。

`carrier`
`Carrier Name`
+++

+++**モバイル属性**
[mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) をダウンロードするか、以下のヘッダーを参照してください。

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
[operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) をダウンロードするか、以下のヘッダーを参照してください。

`os`
`Operating System Type`
+++
