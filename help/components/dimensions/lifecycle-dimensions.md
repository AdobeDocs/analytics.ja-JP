---
title: モバイルライフサイクルディメンション
description: Mobile SDKを使用して収集されたデータに基づくディメンション。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 180
ht-degree: 25%

---

# モバイルライフサイクルディメンション

*このページ参照データは、Adobe Experience Platform Mobile SDKを通じて一般的に追跡されます。 ユーザーエージェントを使用するモバイルデバイス情報については、[ モバイル検索ディメンション ](mobile-dimensions.md)を参照してください。 Mobile SDKを使用して追跡された指標については、[ モバイルライフサイクル指標](../metrics/lifecycle-metrics.md)を参照してください。*

| ライフサイクルディメンション名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| [!UICONTROL 初回起動日] | | |
| [!UICONTROL  デバイス名（SDK） ] | | `a.DeviceName` |
| [!UICONTROL  オペレーティングシステムのバージョン（SDK） ] | | `a.OSVersion` |
| [!UICONTROL 解像度（SDK） ] | | `a.Resolution` |
| [!UICONTROL Sourceの獲得] | | `a.referrer.campaign.source` |
| [!UICONTROL  アプリ ID] | | `a.AppID` |
| [!UICONTROL Mediumの獲得] | | `a.referrer.campaign.medium` |
| [!UICONTROL 取得条件] | | `a.referrer.campaign.term` |
| [!UICONTROL 獲得コンテンツ ] | | `a.refferer.campaign.content` |
| [!UICONTROL 取得名] | | `a.referrer.campaign.name` |
| [!UICONTROL ロケーション（半径 10 km 以内）] | 訪問者の緯度と経度、最初の小数点以下桁まで正確です。 例：`040.9` `-111.9`。 | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL ロケーション（半径 100 m 以内）] | 訪問者の緯度と経度、小数点第3位まで正確です。 例：`040.932` `-111.931`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL ロケーション（半径 1 m 以内）] | 訪問者の緯度と経度、小数点第5位まで正確です。 例：`040.93231` `-111.93152`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL 目標点名] | | `a.loc.poi` |
| [!UICONTROL 目標地点の中心までの距離] | | `a.loc.dist` |
| [!UICONTROL 起動回数] | | `a.Launches` |
| [!UICONTROL 初回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL  アクション名] | | |
| [!UICONTROL  ライフタイム値（evar） ] | | `a.ltv.amount` |
| [!UICONTROL  ビーコン メジャー] | | |
| [!UICONTROL  ビーコン マイナー] | | |
| [!UICONTROL  ビーコン UUID] | | |
| [!UICONTROL  ビーコン近接] | | |
| [!UICONTROL 前回使用からの日数] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 時間帯（SDK） ] | | `a.HourOfDay` |
| [!UICONTROL 曜日（SDK） ] | | `a.DayOfWeek` |
| [!UICONTROL Point of Interest ID] | | |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
