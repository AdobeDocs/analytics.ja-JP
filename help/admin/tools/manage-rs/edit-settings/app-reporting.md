---
description: モバイルアプリケーショントラッキングで使用するディメンションと指標を有効にします。
title: アプリレポート
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
TQID: https://experienceleague.adobe.com/oF-tETs2-MWjSLoo5bVUmrr2nS4N1o2shD4DkMDAVLU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 543
ht-degree: 11%

---

# アプリレポート

アプリレポートのインターフェイスを使用すると、モバイルアプリケーションのトラッキングで使用する専用のライフサイクルディメンションと指標を有効にできます。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** > **[!UICONTROL 設定を編集]** > **[!UICONTROL アプリ管理]** > **[!UICONTROL アプリレポート]**

>[!IMPORTANT]
>
>これらの機能のいずれかを有効にすると、無効にすることはできません。 特定の機能を有効にすると、それぞれのディメンションと指標がAnalysis Workspaceで永続的に使用できるようになります。

## [!UICONTROL  アプリレポート ]

[!UICONTROL  アプリレポート ]のディメンションと指標は、次の目的で使用されます。

* **獲得**: アプリのダウンロードキャンペーンの参照URLを追跡します。
* **ライフサイクル**：各アプリ起動時に測定によって提供されるレポートの基盤レベル。
* **アプリのアクション**: アプリ内アクションに基づくレポートとパス。
* **生涯価値**: アプリのKPI （購入、広告ビュー、ビデオの完成、ソーシャル共有、写真のアップロードなど）を使用して、ユーザーが時間の経過とともにどのように価値を生み出すかを把握します。
* **タイムイベント**：主要なアプリのアクション間（最初の購入までの時間など）の経過時間（アプリ内および合計時間）を測定します。

[!UICONTROL  アプリレポート ]を有効にすると、次のディメンションを使用できます。

* [!UICONTROL  アクション名] （[ エントリ ](/help/components/dimensions/entry-dimensions.md)および[終了](/help/components/dimensions/exit-dimensions.md) ディメンション）
* [!UICONTROL  アプリ ID]
* [!UICONTROL 獲得コンテンツ ]
* [!UICONTROL Mediumの獲得]
* [!UICONTROL 取得名]
* [!UICONTROL Sourceの獲得]
* [!UICONTROL 取得条件]
* [!UICONTROL 曜日（SDK） ]
* [!UICONTROL 初回使用からの日数]
* [!UICONTROL 前回使用からの日数]
* [!UICONTROL  デバイス名（SDK） ]
* [!UICONTROL 時間帯（SDK） ]
* [!UICONTROL 初回起動日]
* [!UICONTROL 起動回数]
* [!UICONTROL  ライフタイム値（evar） ]
* [!UICONTROL  オペレーティングシステムのバージョン（SDK） ]
* [!UICONTROL 解像度（SDK） ]

次の指標を使用できます。

* [!UICONTROL アプリでのアクション時間]
* [!UICONTROL 合計アクション時間]
* [!UICONTROL クラッシュ]
* [!UICONTROL 初回起動]
* [!UICONTROL 起動回数]
* [!UICONTROL ライフタイム値（イベント）]
* [!UICONTROL セッションの長さの合計]
* [!UICONTROL アップグレード]

## [!UICONTROL 場所の追跡]

[!UICONTROL 場所トラッキング ]のディメンションは、次の目的で使用されます。

* 緯度と経度データの追跡
* 特定のPOIを特定、作成、可視化。 ポイントオブインタレストは、モバイル SDK設定ファイルで定義する必要があります。
* Bluetooth ビーコン（UUID、メジャー、マイナー、近接）を追跡します。

[!UICONTROL 場所トラッキング ]を有効にすると、次のディメンションを使用できます。

* [!UICONTROL  ビーコン メジャー] （[ エントリ ](/help/components/dimensions/entry-dimensions.md)および[終了](/help/components/dimensions/exit-dimensions.md) ディメンション）
* [!UICONTROL  ビーコン マイナー] （[ エントリ ](/help/components/dimensions/entry-dimensions.md)および[終了](/help/components/dimensions/exit-dimensions.md) ディメンション）
* [!UICONTROL  ビーコン近接] （[ エントリ ](/help/components/dimensions/entry-dimensions.md)および[終了](/help/components/dimensions/exit-dimensions.md) ディメンション）
* [!UICONTROL  ビーコン UUID] （[ エントリ ](/help/components/dimensions/entry-dimensions.md)および[終了](/help/components/dimensions/exit-dimensions.md) ディメンション）
* [!UICONTROL ロケーション（半径 10 km 以内）]
* [!UICONTROL ロケーション（半径 100 m 以内）]
* [!UICONTROL ロケーション（半径 1 m 以内）]
* [!UICONTROL 目標点名]
* [!UICONTROL 目標地点の中心までの距離]
* [!UICONTROL Point of Interest ID]

## [!UICONTROL 音声とチャットボット ]

[!UICONTROL 音声とチャットボット ]のディメンションと指標を使用すると、AlexaやGoogle ホームなどの音声アシスタントを測定できます。 また、自社製のチャットボットを測定することもできます。 測定プロパティには、次のものが含まれます。

* **ライフサイクル**：起動数やプラットフォームの種類など、任意のアプリの基盤レベルのレポート。
* **会話**：会話に関連する意図、応答、その他の指標とディメンションを測定します。

[!UICONTROL 音声とチャットボット ]を有効にすると、次のディメンションを使用できます。

* [!UICONTROL 音声デバイス機能] （[ エントリ ](/help/components/dimensions/entry-dimensions.md)および[終了](/help/components/dimensions/exit-dimensions.md) ディメンション）
* [!UICONTROL 音声認証]
* [!UICONTROL 音声エラーの種類]
* [!UICONTROL 音声インテント ]
* [!UICONTROL 音声アプリの応答]
* [!UICONTROL 音声言語]

次の指標を使用できます。

* [!UICONTROL 音声終了セッション ]
* [!UICONTROL 音声エラー]
* [!UICONTROL 発音]

## バックグラウンドのヒット数の従来のレポートおよび属性

従来のレポートでは、アプリがバックグラウンドで生成されたヒットは、通常のフォアグラウンドヒットとして扱われます。 レポートに表示され、アトリビューションに影響します。 このレガシー設定は、通常、レガシー実装との一貫性を維持するために望ましいです。

Adobeでは、バックグラウンドヒットが表示されないように、従来のレポートを無効にすることをお勧めします。 分析に背景ヒットを含める場合は、[仮想レポートスイート ](/help/components/vrs/vrs-about.md)設定&#x200B;**[!UICONTROL 背景ヒットを含める]**&#x200B;を有効にできます。
