---
name: Mobile lifecycle metrics
description: Mobile SDK を使用して収集されたデータに基づく指標です。
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 100%

---

# モバイルライフサイクル指標

| ライフサイクル指標名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| 初回起動 | | `a.InstallEvent` |
| アップグレード | | `a.UpgradeEvent` |
| 起動回数 | | `a.LaunchEvent` |
| クラッシュ | | `a.CrashEvent` |
| セッションの長さの合計 | | 未定 |
| 合計アクション時間 | | `a.action.time.total` |
| アプリでのアクション時間 | | `a.action.time.inapp` |
| ライフタイム値（イベント） | | `a.ltv.amount` |

{style="table-layout:auto"}
