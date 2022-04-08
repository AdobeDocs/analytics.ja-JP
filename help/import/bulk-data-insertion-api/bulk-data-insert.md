---
title: 一括データ挿入 API
description: 一括データ挿入 API（BDIA）は Adobe Analytics の機能で、AppMeasurement などのクライアントサイドライブラリを使用する代わりに、多数のファイルからなるサーバーコールデータをアップロードできるものです。これらのバッチファイルでのサーバーコールは、現在の（ライブ）データまたは履歴データのいずれかです。これは、以前のバージョンの Adobe Analytics API に含まれるデータ挿入 API の後継となるもので、拡張性がより高くなっています。
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
source-git-commit: b1ebf6e3548ef73217ffff1cbfb66af82e38fb8f
workflow-type: ht
source-wordcount: '231'
ht-degree: 100%

---

# 一括データ挿入 API

一括データ挿入は、次のようないくつかのユースケースを解決します。

* 以前の Analytics システムからの履歴データの取り込み

* AppMeasurement を使用できないようにする内部分析収集システム。ETL（抽出-変換-読み込み）プロセスを使用してデータをバッチファイルに取り込んだ後、BDIA を使用してそれらを Adobe Analytics にアップロードできます。

* インターネットへの断続的な接続のみ可能なデバイスからのデータ収集。これらのデバイスは、接続が確立されるまでインタラクション内容を保存します。その後、デバイスは BDIA を介して一度にデータをアップロードできます。

データ挿入 API と[一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) はどちらも、サーバーサイドの収集データを Adobe Analytics に送信する手段です。データ挿入 API 呼び出しは、一度に 1 イベントずつおこなわれます。 一括データ挿入 API は、1 行に 1 イベントのイベントデータを含んだ CSV 形式のファイルを受け付けます。 サーバーサイド収集の新しい実装に取り組む場合は、一括データ挿入 API を使用することをお勧めします。
