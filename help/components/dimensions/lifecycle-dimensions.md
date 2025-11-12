---
title: モバイルライフサイクルディメンション
description: Mobile SDKを使用して収集されたデータに基づくディメンション。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 23%

---

# モバイルライフサイクルディメンション

*このページは、Adobe Experience Platform モバイルSDKで一般的に追跡されるデータを参照します。 ユーザーエージェントを使用するモバイルデバイス情報については、[ モバイル参照ディメンション ](mobile-dimensions.md) を参照してください。 Mobile SDKを使用して追跡される指標については、[ モバイルライフサイクル指標 ](../metrics/lifecycle-metrics.md) を参照してください。*

| ライフサイクルディメンション名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| [!UICONTROL  初回開始日 ] | | |
| [!UICONTROL  デバイス名（SDK） ] | | `a.DeviceName` |
| [!UICONTROL  オペレーティングシステムのバージョン（SDK） ] | | `a.OSVersion` |
| [!UICONTROL  解決策（SDK） ] | | `a.Resolution` |
| [!UICONTROL  買収Source] | | `a.referrer.campaign.source` |
| [!UICONTROL  アプリ Id] | | `a.AppID` |
| [!UICONTROL  買収Medium] | | `a.referrer.campaign.medium` |
| [!UICONTROL  取得期間 ] | | `a.referrer.campaign.term` |
| [!UICONTROL  獲得内容 ] | | `a.refferer.campaign.content` |
| [!UICONTROL  取得名 ] | | `a.referrer.campaign.name` |
| [!UICONTROL ロケーション（半径 10 km 以内）] | 訪問者の緯度と経度（小数点第 1 位まで正確）。 例：`040.9` `-111.9`。 | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL ロケーション（半径 100 m 以内）] | 訪問者の緯度と経度（小数第 3 位まで正確）。 例：`040.932` `-111.931`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL ロケーション（半径 1 m 以内）] | 訪問者の緯度と経度。小数第 5 位まで正確です。 例：`040.93231` `-111.93152`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL 目標点名] | | `a.loc.poi` |
| [!UICONTROL 目標地点の中心までの距離] | | `a.loc.dist` |
| [!UICONTROL 起動回数] | | `a.Launches` |
| [!UICONTROL 初回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL  アクション名 ] | | |
| [!UICONTROL  ライフタイム値（evar） ] | | `a.ltv.amount` |
| [!UICONTROL  ビーコンのメジャー ] | | |
| [!UICONTROL  ビーコンのマイナー ] | | |
| [!UICONTROL  ビーコン UUID] | | |
| [!UICONTROL  ビーコンの近接性 ] | | |
| [!UICONTROL 前回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL  時刻（SDK） ] | | `a.HourOfDay` |
| [!UICONTROL  曜日（SDK） ] | | `a.DayOfWeek` |
| [!UICONTROL  目標点 ID] | | |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
