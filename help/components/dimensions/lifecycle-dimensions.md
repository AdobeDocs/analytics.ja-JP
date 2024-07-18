---
title: モバイルライフサイクルディメンション
description: Mobile SDK を使用して収集されたデータに基づくDimension。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 4c472d9a99f15ed253b68124aa31bdc88554d9a5
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 26%

---

# モバイルライフサイクルディメンション

*このページは、Adobe Experience Platform Mobile SDK を通じて一般的に追跡されるデータを参照します。 ユーザーエージェントを使用するモバイルデバイス情報については、[ モバイル参照ディメンション ](mobile-dimensions.md) を参照してください。 Mobile SDK を使用して追跡される指標については、[ モバイルライフサイクル指標 ](../metrics/lifecycle-metrics.md).* を参照してください。

| ライフサイクルディメンション名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| [!UICONTROL  初回開始日 ] | | 未定 |
| [!UICONTROL  デバイス名（SDK） ] | | `a.DeviceName` |
| [!UICONTROL  オペレーティングシステムのバージョン （SDK） ] | | `a.OSVersion` |
| [!UICONTROL  解像度（SDK） ] | | `a.Resolution` |
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
| [!UICONTROL  アクション名 ] | | 未定 |
| [!UICONTROL  ライフタイム値（evar） ] | | `a.ltv.amount` |
| [!UICONTROL  ビーコンのメジャー ] | | 未定 |
| [!UICONTROL  ビーコンのマイナー ] | | 未定 |
| [!UICONTROL  ビーコン UUID] | | 未定 |
| [!UICONTROL  ビーコンの近接性 ] | | 未定 |
| [!UICONTROL 前回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL  時刻（SDK） ] | | `a.HourOfDay` |
| [!UICONTROL  曜日（SDK） ] | | `a.DayOfWeek` |
| [!UICONTROL  目標点 ID] | | 未定 |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
