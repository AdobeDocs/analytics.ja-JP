---
title: データフィードヘッダーのリソース
description: 一部のデータフィードで使用される静的ヘッダーファイル。
translation-type: tm+mt
source-git-commit: 07a9c983b0efa6e75765c1222cf056769417a341
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 0%

---


# データフィードヘッダーのリソース

データフィードには、単なる参照テーブル `hit_data.tsv` や参照テーブル以外のものもあります。 これらの追加のデータファイルは、フィードの設定に依存し、通常、フィード自体にヘッダーファイルを含めません。 次のリストとダウンロードは、これらの追加データファイルの参照です。

## モバイル属性

モバイル属性は、ヒットに含まれるモバイルデバイスのプロパティを表示します。 このファイルは、次の場合に表示されます。

* 動的検索が有効になっています。 組織のサポート委任者は、必要なフィードIDをカスタマーケアに連絡して、動的な検索を有効にできます。
* 列が含まれ `mobile_id` ます。
* 列が除外され `user_agent` ます。 この除外は、DeviceAtlasとのライセンス契約に基づいて必要となります。

リスト `mobile_attributes_headers.tsv`をダウンロードまたは参照するには、こちらを参照してください。

* `mobile_id`
* `Manufacturer`
* `Device`
* `Device Type`
* `Operating System`
* `Diagonal Screen Size`
* `Screen Height`
* `Screen Width`
* `Cookie Support`
* `Color Depth`
* `MP3 Audio Support`
* `AAC Audio Support`
* `AMR Audio Support`
* `Midi Monophonic Audio Support`
* `Midi Polyphonic Audio Support`
* `QCELP Audio Support`
* `GIF87 Image Support`
* `GIF89a Image Support`
* `PNG Image Support`
* `JPG Image Support`
* `3GPP Video Support`
* `MPEG4 Video Support`
* `3GPP2 Video Support`
* `WMV Video Support`
* `MPEG4 Part 2 Video Support`
* `Stream MP4 AAC LC Video Support`
* `Stream 3GP H264 Level 10b Video Support`
* `Stream 3GP AAC LC Video Support`
* `3GP AAC LC Video Support`
* `Stream MP4 H264 Level 11 Video Support`
* `Stream MP4 H264 Level 13 Video Support`
* `Stream 3GP H264 Level 12 Video Support`
* `Stream 3GP H264 Level 11 Video Support`
* `Stream 3GP H264 Level 10 Video Support`
* `Stream 3GP H264 Level 13 Video Support`
* `3GP AMR NB Video Support`
* `3GP AMR WB Video Support`
* `MP4 H264 Level 11 Video Support`
* `3GP H263 Video Support`
* `MP4 H264 Level 13 Video Support`
* `Stream 3GP H263 Video Support`
* `Stream 3GP AMR WB Video Support`
* `3GP H264 Level 10b Video Support`
* `MP4 ACC LC Video Support`
* `Stream 3GP AMR NB Video Support`
* `3GP H264 Level 10 Video Support`
* `3GP H264 Level 13 Video Support`
* `3GP H264 Level 11 Video Support`
* `3GP H264 Level 12 Video Support`
* `Stream HTTP Live Streaming Video Support`