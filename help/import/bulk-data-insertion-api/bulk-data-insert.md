---
title: 一括データ挿入 API
description: Bulk Data Insertion API(BDIA) は、Adobe Analyticsの機能で、AppMeasurement などのクライアント側ライブラリを使用する代わりに、ファイルのバッチでサーバーコールデータをアップロードできます。 これらのバッチファイルのサーバーコールは、現在の（ライブ）データまたは履歴データのいずれかです。 これは、以前のバージョンのAdobe Analytics API の Data Insertion API の拡張性の高い後継ツールです。
solution: Analytics
feature: API
source-git-commit: d8603ddd6cee2ccc930281003d9ff1befa15c95c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 27%

---


# 一括データ挿入 API

一括データ挿入は、次のような複数の使用例を解決します。

* 以前の Analytics システムからの履歴データの取り込み

* AppMeasurement を使用できないようにする内部分析収集システム。 Extract-Transform-Load(ETL) プロセスを使用してデータをバッチファイルに取り込んだ後、BDIA を使用してそれらをAdobe Analyticsにアップロードできます。

* インターネットへの断続的な接続のみを持つデバイスからのデータ収集。 これらのデバイスは、接続を受け取るまでインタラクションを保存します。 その後、デバイスは BDIA を介して一度にデータをアップロードできます。

Data Insertion API および [一括データ挿入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html?lang=ja#!AdobeDocs/analytics-2.0-apis/master/bdia.md)は、どちらの方法でも、サーバー側の収集データをAdobe Analyticsに送信できます。 データ挿入 API 呼び出しは、一度に 1 イベントずつおこなわれます。 一括データ挿入 API は、1 行に 1 イベントのイベントデータを含んだ CSV 形式のファイルを受け付けます。 サーバーサイド収集の新しい実装に取り組む場合は、一括データ挿入 API を使用することをお勧めします。