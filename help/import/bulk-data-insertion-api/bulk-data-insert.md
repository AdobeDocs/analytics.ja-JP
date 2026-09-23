---
title: 一括データ挿入 API
description: Bulk Data Insertion API （BDIA）は、Adobe Analyticsの機能で、AppMeasurementなどのクライアントサイドのライブラリを使用する代わりに、サーバー呼び出しデータをファイルのバッチでアップロードできます。
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: 'https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
    internal-label: Data sources
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 53%
---
# 一括データ挿入 API

一括データ挿入は、次のようないくつかのユースケースを解決します。

* 以前の Analytics システムからの履歴データの取り込み

* AppMeasurement の使用が現実的でない内部分析収集システム。 ETL（抽出-変換-読み込み）プロセスを使用してデータをバッチファイルに取り込んだ後、BDIA を使用してそれらを Adobe Analytics にアップロードできます。

* インターネットへの断続的な接続のみ可能なデバイスからのデータ収集。 これらのデバイスは、接続が確立されるまでインタラクション内容を保存します。 その後、デバイスは BDIA を介して一度にデータをアップロードできます。

Data Insertion APIと[Bulk Data Insertion API](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/)はどちらも、Adobe Analyticsにサーバーサイドのコレクションデータを送信するメソッドです。 データ挿入 API 呼び出しは、一度に 1 イベントずつおこなわれます。 Bulk Data Insertion API は、1 行につき 1 件のイベントデータを含む CSV 形式のファイルを受け付けます。 サーバーサイドコレクションの新しい実装を行う場合は、AdobeでBulk Data Insertion APIを使用することをお勧めします。

認証、エンドポイント、ファイル形式、列参照、およびトラブルシューティングについては、Adobe Developerの[Bulk Data Insertion API](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/) ドキュメントを参照してください。
