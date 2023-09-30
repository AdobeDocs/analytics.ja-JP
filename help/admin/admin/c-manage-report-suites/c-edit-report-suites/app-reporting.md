---
description: ディメンションと指標をモバイルアプリケーションのトラッキングで使用できるようにします。
title: アプリレポート
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 18%

---

# アプリレポート

アプリレポートインターフェイスを使用すると、モバイルアプリケーションの追跡での使用専用のライフサイクルディメンションおよび指標を有効にできます。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** > **[!UICONTROL 設定を編集]** > **[!UICONTROL アプリ管理]** > **[!UICONTROL アプリレポート]**

>[!IMPORTANT]
>
>これらの機能のいずれかを有効にすると、無効にすることはできません。 特定の機能を有効にすると、それぞれのディメンションと指標をAnalysis Workspaceで永続的に使用できるようになります。

## [!UICONTROL アプリレポート]

[!UICONTROL アプリレポート] ディメンションと指標は、次の目的で使用されます。

* **獲得**：アプリのダウンロードキャンペーンの参照 URL を追跡します。
* **ライフサイクル**：各アプリの起動時に送信される測定によって提供されるレポートの基盤レベル。
* **アプリのアクション**：アプリ内アクションに基づくレポートとパス。
* **ライフタイム値**：アプリ KPI（購入、広告ビュー、ビデオ完了、ソーシャル共有、写真のアップロードなど）を使用して、時間の経過と共にユーザーがどのように価値を生み出すかを理解します。
* **時間計測イベント**：アプリの主要なアクション（初回購入までの時間など）の間に経過した時間（アプリ内および合計時間）を測定します。

を有効にした場合 [!UICONTROL アプリレポート]に値を指定する場合、次のディメンションを使用できます。

* [!UICONTROL アクション名] ( [入口](/help/components/dimensions/entry-dimensions.md) および [終了](/help/components/dimensions/exit-dimensions.md) ディメンション )
* [!UICONTROL アプリケーション ID]
* [!UICONTROL 獲得コンテンツ]
* [!UICONTROL 獲得メディア]
* [!UICONTROL 獲得名]
* [!UICONTROL 獲得参照元]
* [!UICONTROL 獲得キーワード]
* [!UICONTROL 曜日（SDK）]
* [!UICONTROL 初回使用からの日数]
* [!UICONTROL 前回使用からの日数]
* [!UICONTROL 機種名（SDK）]
* [!UICONTROL 時間帯（SDK）]
* [!UICONTROL 初回起動日]
* [!UICONTROL 起動回数]
* [!UICONTROL 全期間値（eVar）]
* [!UICONTROL オペレーティングシステムのバージョン（SDK）]
* [!UICONTROL 解像度 (SDK)]

以下の指標を使用できます。

* [!UICONTROL アプリでのアクション時間]
* [!UICONTROL 合計アクション時間]
* [!UICONTROL クラッシュ]
* [!UICONTROL 初回起動]
* [!UICONTROL 起動回数]
* [!UICONTROL ライフタイム値（イベント）]
* [!UICONTROL セッションの長さの合計]
* [!UICONTROL アップグレード]

## [!UICONTROL ロケーションの追跡]

[!UICONTROL ロケーションの追跡] ディメンションは、次の目的で使用されます。

* 緯度と経度のデータを追跡する
* 特定の目標地点を特定、作成、視覚化します。 目標地点は、モバイル SDK 設定ファイルで定義する必要があります。
* Bluetooth ビーコン（UUID、Major、Minor および Proximity）を追跡します。

を有効にした場合 [!UICONTROL ロケーションの追跡]に値を指定する場合、次のディメンションを使用できます。

* [!UICONTROL ビーコンの Major] ( [入口](/help/components/dimensions/entry-dimensions.md) および [終了](/help/components/dimensions/exit-dimensions.md) ディメンション )
* [!UICONTROL ビーコンの Minor] ( [入口](/help/components/dimensions/entry-dimensions.md) および [終了](/help/components/dimensions/exit-dimensions.md) ディメンション )
* [!UICONTROL ビーコンの Proximity] ( [入口](/help/components/dimensions/entry-dimensions.md) および [終了](/help/components/dimensions/exit-dimensions.md) ディメンション )
* [!UICONTROL ビーコンの UUID] ( [入口](/help/components/dimensions/entry-dimensions.md) および [終了](/help/components/dimensions/exit-dimensions.md) ディメンション )
* [!UICONTROL ロケーション（半径 10 km 以内）]
* [!UICONTROL ロケーション（半径 100 m 以内）]
* [!UICONTROL ロケーション（半径 1 m 以内）]
* [!UICONTROL 目標点名]
* [!UICONTROL 目標地点の中心までの距離]
* [!UICONTROL 目標点 ID]

## [!UICONTROL ボイスおよびチャットボット]

[!UICONTROL ボイスおよびチャットボット] ディメンションと指標を使用すると、AlexaやGoogle Home などの音声アシスタントを測定できます。 また、自家製のチャットボットを測定することもできます。 測定プロパティには以下が含まれます。

* **ライフサイクル**：起動数やプラットフォームタイプなど、任意のアプリに関するレポートの基盤レベル。
* **会話**：会話に関連する目的、応答、その他の指標およびディメンションを測定します。

を有効にした場合 [!UICONTROL ボイスおよびチャットボット]に値を指定する場合、次のディメンションを使用できます。

* [!UICONTROL ボイスデバイスの機能] ( [入口](/help/components/dimensions/entry-dimensions.md) および [終了](/help/components/dimensions/exit-dimensions.md) ディメンション )
* [!UICONTROL 音声認証]
* [!UICONTROL ボイスエラータイプ]
* [!UICONTROL ボイスインテント]
* [!UICONTROL ボイスアプリの応答]
* [!UICONTROL ボイス言語]

以下の指標を使用できます。

* [!UICONTROL ボイスセッションを終了]
* [!UICONTROL ボイスエラー]
* [!UICONTROL ボイス発話]

## バックグラウンドのヒット数の従来のレポートおよび属性

従来のレポートとは、アプリがバックグラウンドにあるときに生成されたヒットは、通常のフォアグラウンドヒットとして扱われることを意味します。 レポートに表示され、アトリビューションに影響を与えます。 このレガシー設定は、レガシー実装との一貫性を維持するために一般的に望ましい設定です。

Adobeは、バックグラウンドヒットが表示されないように、従来のレポートを無効にすることをお勧めします。 分析にバックグラウンドヒットを含める場合は、 [仮想レポートスイート](/help/components/vrs/vrs-about.md) 設定 **[!UICONTROL バックグラウンドヒットを含める]**.
