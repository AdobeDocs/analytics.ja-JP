---
title: 一括データ挿入 API
description: Bulk Data Insertion API （BDIA）は、Adobe Analyticsの機能で、AppMeasurementなどのクライアントサイドのライブラリを使用する代わりに、サーバー呼び出しデータをファイルのバッチでアップロードできます。
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 85%

---

# 一括データ挿入 API

一括データ挿入は、次のようないくつかのユースケースを解決します。

* 以前の Analytics システムからの履歴データの取り込み

* AppMeasurement を使用できないようにする内部分析収集システム。 ETL（抽出-変換-読み込み）プロセスを使用してデータをバッチファイルに取り込んだ後、BDIA を使用してそれらを Adobe Analytics にアップロードできます。

* インターネットへの断続的な接続のみ可能なデバイスからのデータ収集。 これらのデバイスは、接続が確立されるまでインタラクション内容を保存します。 その後、デバイスは BDIA を介して一度にデータをアップロードできます。

データ挿入 API と[一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) はどちらも、サーバーサイドの収集データを Adobe Analytics に送信する手段です。 データ挿入 API 呼び出しは、一度に 1 イベントずつおこなわれます。 一括データ挿入 API は、1 行に 1 イベントのイベントデータを含んだ CSV 形式のファイルを受け付けます。 サーバーサイド収集の新しい実装に取り組む場合は、一括データ挿入 API を使用することをお勧めします。
