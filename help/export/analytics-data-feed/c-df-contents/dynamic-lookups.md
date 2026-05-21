---
title: 動的検索
description: 動的参照とは何か、およびそれらを有効にする方法について説明します。 キャリア、モバイル属性、およびオペレーティングシステムの種類が含まれます。
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
TQID: https://experienceleague.adobe.com/hKuBXw8dX419msIgSjvd3Dl5uE4rJS6nouIbR18RmVo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 306
ht-degree: 20%

---

# 動的検索

動的ルックアップを使用すると、データフィード内の追加のルックアップファイルを受信できます。それ以外の場合は使用できません。 この設定では、各データフィードファイルで次のルックアップテーブルを送信できます。

* **キャリア名**: `carrier`列の追加のコンテキストを提供します。 含まれているファイル名は`carrier.tsv`です。
* **モバイル属性**：各モバイルデバイスで追跡されているすべての機能を含む、`mobile_id`列の追加のコンテキストを提供します。 含まれているファイル名は`mobile_attributes.tsv`です。
* **オペレーティングシステムの種類**: `os`列の代替コンテキストを提供します。 `operating_systems.tsv`と`operating_system_type.tsv`の両方が`os`列をキーとして使用していますが、`operating_system_type.tsv`のみが動的ルックアップです。

## 動的ルックアップの有効化 {#enable-dynamic-lookups}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_dynamic_lookups"
>title="動的ルックアップの有効化"
>abstract="追加のルックアップファイルをデータフィードで受け取る場合は、このオプションを選択します。それ以外の場合、このオプションは使用できません。 この設定では、各データフィードファイルで次のルックアップテーブルを送信できます。<ul><li>通信事業者の名前</li><li>モバイル属性</li><li>オペレーティングシステムの種類</li></ul>"

<!-- markdownlint-enable MD034 -->

前述のルックアップファイルを受け取る場合は、次のすべての前提条件を満たす必要があります。

* キー列はデータフィードに含める必要があります。
   * `carrier.tsv`の場合、`carrier`を含める必要があります。
   * `mobile_attributes.tsv`の場合、`mobile_id`を含める必要があります。
   * `operating_system_type.tsv`の場合、`os`を含める必要があります。
* 次の列は&#x200B;**除外**&#x200B;である必要があります。 これらの列のいずれかがデータフィードに含まれている場合、`mobile_attributes.tsv`動的ルックアップは含まれません。
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

データフィードが列の包含と除外の要件を満たしたら、カスタマーサポートにデータフィード IDを連絡して、動的検索を有効にするようにリクエストします。

## ルックアップヘッダー参照

これらのルックアップファイルの列ヘッダーは時間の経過とともに変化しないため、各データフィードファイルにヘッダーは含まれません。 これらの列ヘッダーを参照として使用するか、それぞれの`.tsv` ファイルをダウンロードします。

+++**通信事業者名**
[carrier_headers.tsv](assets/carrier_headers.tsv)をダウンロードするか、以下のヘッダーを参照してください。

`carrier`
`Carrier Name`
+++

+++**モバイル属性**
[mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv)をダウンロードするか、以下のヘッダーを参照してください。

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

+++**オペレーティング システムの種類**
[operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv)をダウンロードするか、以下のヘッダーを参照してください。

`os`
`Operating System Type`
+++
