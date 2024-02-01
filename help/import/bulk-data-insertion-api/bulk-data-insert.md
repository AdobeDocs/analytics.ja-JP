---
title: 一括データ挿入 API
description: Bulk Data Insertion API(BDIA) は、Adobe Analyticsの機能で、AppMeasurementなどのクライアント側ライブラリを使用する代わりに、サーバー呼び出しデータをファイルのバッチでアップロードできます。
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 84%

---

# 一括データ挿入 API

一括データ挿入は、次のようないくつかのユースケースを解決します。

* 以前の Analytics システムからの履歴データの取り込み

* AppMeasurement を使用できないようにする内部分析収集システム。ETL（抽出-変換-読み込み）プロセスを使用してデータをバッチファイルに取り込んだ後、BDIA を使用してそれらを Adobe Analytics にアップロードできます。

* インターネットへの断続的な接続のみ可能なデバイスからのデータ収集。これらのデバイスは、接続が確立されるまでインタラクション内容を保存します。その後、デバイスは BDIA を介して一度にデータをアップロードできます。

データ挿入 API と[一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) はどちらも、サーバーサイドの収集データを Adobe Analytics に送信する手段です。データ挿入 API 呼び出しは、一度に 1 イベントずつおこなわれます。 一括データ挿入 API は、1 行に 1 イベントのイベントデータを含んだ CSV 形式のファイルを受け付けます。 サーバーサイド収集の新しい実装に取り組む場合は、一括データ挿入 API を使用することをお勧めします。
