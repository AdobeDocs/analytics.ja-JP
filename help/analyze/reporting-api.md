---
description: レポート API のリソースとリンクです。
title: Analytics レポート API
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: a9d892ab8caaeb797fbbd9b5aa136c5dab76f8bd
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 73%

---

# Analytics レポート API

Adobe Analytics APIのドキュメントは、[Adobe I/O](https://adobe.io/analytics-apis/docs)にあります。

## Analytics APIの比較

| **API のタイプ** | **完全処理済み** | **リアルタイム** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **説明** | Analytics インターフェイスで利用できる、完全に処理済みで、ファイナライズされたデータ。 | 数秒間の収集で部分的に処理された、制限された指標。 | 数秒間の収集で部分的に処理されたヒットデータ。 | 大量のデータエクスポートを引き出すために使用される、完全に処理済みで、ファイナライズされたデータ。 |
| [**遅延**](/help/technotes/latency.md) | 30 ～ 90 分 | 数秒 ～ 10 分 | 数秒 ～ 10 分 | 90分以上 |
| **処理の完了** | フル | 部分的 | 部分的 | フル |
| **レポートインターフェイス** | Analysis Workspace、Reports &amp; Analytics、Report Builder、API | Reports &amp; Analytics、Report Builder、1.4 APIのリアルタイムレポート | API のみ | Data Warehouse、API |
| **データの精度** | 集計済み | 集計済み | ヒットレベル | 集計済み |
| **訪問者プロファイルの処理** | ○ | × | × | ○ |
| **セグメントのサポート** | ○ | × | × | 部分的 |
