---
description: レポート API のリソースとリンクです。
title: Analytics レポート API
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: 8f25dfefbc6fba1fb525d2e9e0fce654e21ef362
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 92%

---

# Analytics レポート API

Adobe Analytics API のドキュメントは、 [Adobe開発者](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Analytics API の比較

| **API のタイプ** | **完全処理済み** | **リアルタイム** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **説明** | Analytics インターフェイスで利用できる、完全に処理済みで、ファイナライズされたデータ。 | 数秒間の収集で部分的に処理された、制限された指標。 | 数秒間の収集で部分的に処理されたヒットデータ。 | 大量のデータエクスポートを引き出すために使用される、完全に処理済みで、ファイナライズされたデータ。 |
| [**遅延**](/help/technotes/latency.md) | 30 ～ 90 分 | 数秒 ～ 10 分 | 数秒 ～ 10 分 | 90 分以上 |
| **処理の完了** | フル | 部分的 | 部分的 | フル |
| **レポートインターフェイス** | Analysis Workspace、Reports &amp; Analytics、Report Builder、API | Reports &amp; Analytics、Report Builder、1.4 API のリアルタイムレポート | API のみ | Data Warehouse、API |
| **データの精度** | 集計済み | 集計済み | ヒットレベル | 集計済み |
| **訪問者プロファイルの処理** | ○ | × | × | ○ |
| **セグメントのサポート** | ○ | × | × | 部分的 |
