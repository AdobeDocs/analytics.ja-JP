---
title: モバイルライフサイクル指標
description: Mobile SDK を使用して収集されたデータに基づく指標です。
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 100%

---

# モバイルライフサイクル指標

| ライフサイクル指標名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| 初回起動 | | `a.InstallEvent` |
| アップグレード | | `a.UpgradeEvent` |
| 起動回数 | | `a.LaunchEvent` |
| クラッシュ | | `a.CrashEvent` |
| セッションの長さの合計 | | |
| 合計アクション時間 | | `a.action.time.total` |
| アプリでのアクション時間 | | `a.action.time.inapp` |
| ライフタイム値（イベント） | | `a.ltv.amount` |

{style="table-layout:auto"}
