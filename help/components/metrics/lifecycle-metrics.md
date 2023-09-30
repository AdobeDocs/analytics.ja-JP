---
name: Mobile lifecycle metrics
description: Mobile SDK で収集されたデータに基づく指標です。
feature: Metrics
source-git-commit: fa9ba599ccc3d6fe1176e6b2ec20457f30cb5959
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 52%

---

# モバイルのライフサイクル指標

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
