---
title: モバイルライフサイクルディメンション
description: Mobile SDKを使用して収集されたデータに基づくディメンション。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 4c472d9a99f15ed253b68124aa31bdc88554d9a5
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 26%

---

# モバイルライフサイクルディメンション

*このページは、Adobe Experience Platform モバイルSDKで一般的に追跡されるデータを参照します。 ユーザーエージェントを使用するモバイルデバイス情報については、[&#x200B; モバイル参照ディメンション &#x200B;](mobile-dimensions.md) を参照してください。 Mobile SDKを使用して追跡される指標については、[&#x200B; モバイルライフサイクル指標 &#x200B;](../metrics/lifecycle-metrics.md) を参照してください。*

| ライフサイクルディメンション名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| [!UICONTROL &#x200B; 初回開始日 &#x200B;] | | 未定 |
| [!UICONTROL &#x200B; デバイス名（SDK） &#x200B;] | | `a.DeviceName` |
| [!UICONTROL &#x200B; オペレーティングシステムのバージョン（SDK） &#x200B;] | | `a.OSVersion` |
| [!UICONTROL &#x200B; 解決策（SDK） &#x200B;] | | `a.Resolution` |
| [!UICONTROL &#x200B; 買収Source] | | `a.referrer.campaign.source` |
| [!UICONTROL &#x200B; アプリ Id] | | `a.AppID` |
| [!UICONTROL &#x200B; 買収Medium] | | `a.referrer.campaign.medium` |
| [!UICONTROL &#x200B; 取得期間 &#x200B;] | | `a.referrer.campaign.term` |
| [!UICONTROL &#x200B; 獲得内容 &#x200B;] | | `a.refferer.campaign.content` |
| [!UICONTROL &#x200B; 取得名 &#x200B;] | | `a.referrer.campaign.name` |
| [!UICONTROL ロケーション（半径 10 km 以内）] | 訪問者の緯度と経度（小数点第 1 位まで正確）。 例：`040.9` `-111.9`。 | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL ロケーション（半径 100 m 以内）] | 訪問者の緯度と経度（小数第 3 位まで正確）。 例：`040.932` `-111.931`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL ロケーション（半径 1 m 以内）] | 訪問者の緯度と経度。小数第 5 位まで正確です。 例：`040.93231` `-111.93152`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL 目標点名] | | `a.loc.poi` |
| [!UICONTROL 目標地点の中心までの距離] | | `a.loc.dist` |
| [!UICONTROL 起動回数] | | `a.Launches` |
| [!UICONTROL 初回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL &#x200B; アクション名 &#x200B;] | | 未定 |
| [!UICONTROL &#x200B; ライフタイム値（evar） &#x200B;] | | `a.ltv.amount` |
| [!UICONTROL &#x200B; ビーコンのメジャー &#x200B;] | | 未定 |
| [!UICONTROL &#x200B; ビーコンのマイナー &#x200B;] | | 未定 |
| [!UICONTROL &#x200B; ビーコン UUID] | | 未定 |
| [!UICONTROL &#x200B; ビーコンの近接性 &#x200B;] | | 未定 |
| [!UICONTROL 前回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL &#x200B; 時刻（SDK） &#x200B;] | | `a.HourOfDay` |
| [!UICONTROL &#x200B; 曜日（SDK） &#x200B;] | | `a.DayOfWeek` |
| [!UICONTROL &#x200B; 目標点 ID] | | 未定 |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
