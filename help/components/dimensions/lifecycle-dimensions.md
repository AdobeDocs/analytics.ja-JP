---
title: モバイルライフサイクルディメンション
description: Mobile SDKを使用して収集されたデータに基づくディメンション。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: 'https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 8%
---
# モバイルライフサイクルディメンション

>[!BEGINSHADEBOX]

*このページは、Adobe Experience Platform Mobile SDKを通じて一般的に追跡されるデータを参照しています。 ユーザーエージェントを使用するモバイルデバイス情報については、[ モバイル検索ディメンション ](mobile-dimensions.md)を参照してください。 Mobile SDKを使用して追跡された指標については、[ モバイルライフサイクル指標](../metrics/lifecycle-metrics.md)を参照してください。*

>[!ENDSHADEBOX]

| ライフサイクルディメンション名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| **[!UICONTROL 初回起動日]** | アプリがインストールまたは再インストールされた後に最初に実行された日付（`M/d/yyyy`形式）。 | `a.InstallDate` |
| **[!UICONTROL デバイス名（SDK）]** | SDKが収集するデバイス名。 | `a.DeviceName` |
| **[!UICONTROL オペレーティングシステムのバージョン（SDK）]** | SDKが収集するオペレーティングシステムの名前とバージョン。 | `a.OSVersion` |
| **[!UICONTROL 解像度（SDK）]** | デバイスの画面解像度（ピクセル単位、幅×高さ）。 | `a.Resolution` |
| **[!UICONTROL Sourceの獲得]** | ニュースレターやソーシャルメディアネットワークなどのアプリ獲得キャンペーンのオリジナルリファラー。 | `a.referrer.campaign.source` |
| **[!UICONTROL アプリ ID]** | アプリの名前とバージョン （形式：`AppName BundleVersion (app version code)`）。 例えば、`MyAppName 1.1(1)` のように設定します。 | `a.AppID` |
| **[!UICONTROL Mediumの獲得]** | バナーやメールなど、アプリ獲得キャンペーンのマーケティングメディア。 | `a.referrer.campaign.medium` |
| **[!UICONTROL 取得条件]** | アプリ獲得キャンペーンに関連する有料キーワードなどの用語。 | `a.referrer.campaign.term` |
| **[!UICONTROL 獲得コンテンツ]** | アプリ獲得リンクを表示するコンテンツの名前またはID。 | `a.referrer.campaign.content` |
| **[!UICONTROL 取得名]** | アプリ獲得キャンペーンの名前。 | `a.referrer.campaign.name` |
| **[!UICONTROL ロケーション（半径 10 km 以内）]** | 訪問者の緯度と経度、最初の小数点以下桁まで正確です。 例：`040.9` `-111.9`。 | `a.loc.lat.a` + `a.loc.lon.a` |
| **[!UICONTROL ロケーション（半径 100 m 以内）]** | 訪問者の緯度と経度、小数点第3位まで正確です。 例：`040.932` `-111.931`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| **[!UICONTROL ロケーション（半径 1 m 以内）]** | 訪問者の緯度と経度、小数点第5位まで正確です。 例：`040.93231` `-111.93152`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| **[!UICONTROL 目標点名]** | デバイスが置かれているPOI （Point of Interest）の名前。 [Places拡張機能](https://developer.adobe.com/client-sdks/solution/places/)を使用する場合、この値はPlaces地域名です。 | `a.loc.poi` |
| **[!UICONTROL 目標地点の中心までの距離]** | デバイスと、そのデバイスが置かれている注目点の中心との間の距離。 | `a.loc.dist` |
| **[!UICONTROL 起動回数]** | アプリが起動したか、バックグラウンドから持ち出された回数。 | `a.Launches` |
| **[!UICONTROL 初回使用からの日数]** | アプリが最初に実行されてからの日数。 | `a.DaysSinceFirstUse` |
| **[!UICONTROL アクション名]** | `trackAction` コールで送信されたアクションの名前。 | `a.action` |
| **[!UICONTROL ライフタイム値（evar）]** | ユーザーの生涯価値（生涯購入、広告の閲覧、動画の完成、ソーシャルシェアなど）。 | `a.ltv.amount` |
| **[!UICONTROL ビーコン メジャー]** | デバイスが近いビーコンのメジャーID。 | `a.beacon.major` |
| **[!UICONTROL ビーコン マイナー]** | デバイスが近いビーコンのマイナーID。 | `a.beacon.minor` |
| **[!UICONTROL ビーコン UUID]** | デバイスが近いビーコンのUUID。 | `a.beacon.uuid` |
| **[!UICONTROL ビーコン近接]** | ビーコンにデバイスの近接：`0` （不明）、`1` （即時）、`2` （近接）、または`3` （遠方）。 | `a.beacon.prox` |
| **[!UICONTROL 前回使用からの日数]** | アプリが最後に使用されてからの日数。 | `a.DaysSinceLastUse` |
| **[!UICONTROL 時間帯（SDK）]** | アプリが起動された時刻（24時間形式）。 ピーク時の使用時間を決定する時間分割に便利です。 | `a.HourOfDay` |
| **[!UICONTROL 曜日（SDK）]** | アプリが起動した週の日付。 | `a.DayOfWeek` |
| **[!UICONTROL Point of Interest ID]** | デバイスが置かれているPOIのID。 [Places拡張機能](https://developer.adobe.com/client-sdks/solution/places/)を使用する場合、この値はPlaces領域IDです。 | `a.loc.poi.id` |

>[!NOTE]
>
>これらのディメンションの一部は、従来のMobile Services SDK（4.x）のメソッドによって入力されますが、これはサポートされなくなりました。 Adobe Experience Platform Mobile SDKでは、次の項目は自動入力されません。
>
>* **獲得ディメンション** （[!UICONTROL 獲得Source]、[!UICONTROL Medium]、[!UICONTROL 条件]、[!UICONTROL  コンテンツ ]、および[!UICONTROL 名前]）: モバイルアプリ獲得によって入力されました。モバイルアプリ獲得は、モバイルSDK [でサポートされていません](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/comparison/)。
>* **[!UICONTROL 場所] ディメンションと[!UICONTROL 目標点までの距離]**: 4.x `trackLocation` メソッドが入力されました。 Mobile SDKは、このメソッドを[Places拡張機能](https://developer.adobe.com/client-sdks/solution/places/)に置き換えます。これにより、[!UICONTROL Point of Interest Name]と[!UICONTROL Point of Interest ID]が設定されます。
>* **[!UICONTROL ライフタイム値（evar）]**: 4.x `trackLifetimeValueIncrease` メソッドによって入力されました。
>* **ビーコン ディメンション** （[!UICONTROL  ビーコン メジャー]、[!UICONTROL  マイナー]、[!UICONTROL UUID]、および[!UICONTROL 近接]）: 4.x `trackBeacon` メソッドによって入力されました。 モバイル SDKでビーコン データを送信するには、[ ビーコンのトラッキング ](https://developer.adobe.com/client-sdks/solution/adobe-analytics/track-beacon/)を参照してください。
>
>詳しくは、[Adobe Mobile Library （v4）からExperience Platform Analyticsへの移行](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/)を参照してください。
