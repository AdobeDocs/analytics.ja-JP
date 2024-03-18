---
title: モバイルライフサイクルディメンション
description: Dimensionは、Mobile SDK を使用して収集されたデータに基づいています。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 4c472d9a99f15ed253b68124aa31bdc88554d9a5
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 26%

---

# モバイルライフサイクルディメンション

*Adobe Experience Platform Mobile SDK で一般的に追跡される、このページ参照データです。 ユーザーエージェントを使用するモバイルデバイス情報については、 [モバイル参照ディメンション](mobile-dimensions.md). Mobile SDK を使用して追跡する指標については、 [モバイルのライフサイクル指標](../metrics/lifecycle-metrics.md).*

| ライフサイクルディメンション名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| [!UICONTROL 初回起動日] | | 未定 |
| [!UICONTROL デバイス名 (SDK)] | | `a.DeviceName` |
| [!UICONTROL オペレーティングシステムのバージョン (SDK)] | | `a.OSVersion` |
| [!UICONTROL 解像度 (SDK)] | | `a.Resolution` |
| [!UICONTROL 獲得ソース] | | `a.referrer.campaign.source` |
| [!UICONTROL アプリ ID] | | `a.AppID` |
| [!UICONTROL 獲得メディア] | | `a.referrer.campaign.medium` |
| [!UICONTROL 獲得キーワード] | | `a.referrer.campaign.term` |
| [!UICONTROL 獲得コンテンツ] | | `a.refferer.campaign.content` |
| [!UICONTROL 獲得名] | | `a.referrer.campaign.name` |
| [!UICONTROL ロケーション（半径 10 km 以内）] | 訪問者の緯度と経度で、最初の小数点以下の桁数の正確さです。 例： `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL ロケーション（半径 100 m 以内）] | 訪問者の緯度と経度で、小数点以下 3 桁までの精度です。 例： `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL ロケーション（半径 1 m 以内）] | 訪問者の緯度と経度（小数点以下 5 桁までの精度）。 例： `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL 目標点名] | | `a.loc.poi` |
| [!UICONTROL 目標地点の中心までの距離] | | `a.loc.dist` |
| [!UICONTROL 起動回数] | | `a.Launches` |
| [!UICONTROL 初回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL アクション名] | | 未定 |
| [!UICONTROL 全期間値 (eVar)] | | `a.ltv.amount` |
| [!UICONTROL ビーコンの Major] | | 未定 |
| [!UICONTROL ビーコンの Minor] | | 未定 |
| [!UICONTROL ビーコンの UUID] | | 未定 |
| [!UICONTROL ビーコンの Proximity] | | 未定 |
| [!UICONTROL 前回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 時間帯 (SDK)] | | `a.HourOfDay` |
| [!UICONTROL 曜日 (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL 目標点 ID] | | 未定 |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
