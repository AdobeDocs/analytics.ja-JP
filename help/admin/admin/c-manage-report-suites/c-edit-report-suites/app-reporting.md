---
description: モバイルアプリケーションのトラッキングで使用するディメンションと指標を有効にします。
title: アプリレポート
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 13%

---

# アプリレポート

アプリレポートインターフェイスを使用すると、モバイルアプリケーションのトラッキング専用のライフサイクルディメンションと指標を有効にできます。

**[!UICONTROL Analytics]**/**[!UICONTROL 管理者]**/**[!UICONTROL レポートスイート]**/**[!UICONTROL 設定編集]**/**[!UICONTROL アプリ管理]**/**[!UICONTROL アプリレポート]**

>[!IMPORTANT]
>
>これらの機能を有効にすると、無効にできなくなります。 特定の機能を有効にすると、それぞれのディメンションと指標をAnalysis Workspaceで永続的に使用できるようになります。

## [!UICONTROL  アプリレポート ]

[!UICONTROL  アプリレポート ] のディメンションと指標は、次の目的で使用されます。

* **獲得**：アプリのダウンロードキャンペーン用の参照 URL をトラッキングします。
* **ライフサイクル**：各アプリのローンチ時に送信される測定によって提供されるレポートの基盤レベル。
* **アプリのアクション**：アプリ内アクションに基づくレポートとパス。
* **生涯価値**：アプリ KPI （購入、広告表示、ビデオ完了、ソーシャル共有、写真のアップロードなど）を使用して、ユーザーが時間の経過と共に価値を生み出す方法を説明します。
* **タイムドイベント**：主要なアプリアクションの合間（初回購入までの時間など）に経過した時間（アプリ内および合計時間）を測定します。

[!UICONTROL  アプリレポート ] を有効にすると、次のディメンションを使用できます。

* [!UICONTROL  アクション名 ] （[ 入口 ](/help/components/dimensions/entry-dimensions.md) および [ 出口 ](/help/components/dimensions/exit-dimensions.md) ディメンションを含む）
* [!UICONTROL  アプリ Id]
* [!UICONTROL  獲得内容 ]
* [!UICONTROL  買収Medium]
* [!UICONTROL  取得名 ]
* [!UICONTROL  買収Source]
* [!UICONTROL  取得期間 ]
* [!UICONTROL  曜日（SDK） ]
* [!UICONTROL 初回使用からの日数]
* [!UICONTROL 前回使用からの日数]
* [!UICONTROL  デバイス名（SDK） ]
* [!UICONTROL  時刻（SDK） ]
* [!UICONTROL  初回開始日 ]
* [!UICONTROL 起動回数]
* [!UICONTROL  ライフタイム値（evar） ]
* [!UICONTROL  オペレーティングシステムのバージョン （SDK） ]
* [!UICONTROL  解像度（SDK） ]

以下の指標を使用できます。

* [!UICONTROL アプリでのアクション時間]
* [!UICONTROL 合計アクション時間]
* [!UICONTROL クラッシュ]
* [!UICONTROL 初回起動]
* [!UICONTROL 起動回数]
* [!UICONTROL ライフタイム値（イベント）]
* [!UICONTROL セッションの長さの合計]
* [!UICONTROL アップグレード]

## [!UICONTROL  位置のトラッキング ]

[!UICONTROL  位置のトラッキング ] ディメンションは、次の目的で使用されます。

* 緯度と経度のデータを追跡
* 特定の目標地点を特定、作成および視覚化します。 目標点は、Mobile SDK 設定ファイルで定義する必要があります。
* Bluetooth ビーコン（UUID、Major、Minor および Proximity）を追跡します。

[!UICONTROL  位置追跡 ] を有効にすると、次のディメンションを使用できます。

* [!UICONTROL  ビーコンのメジャー ] （[ 入口 ](/help/components/dimensions/entry-dimensions.md) ディメンションと [ 出口 ](/help/components/dimensions/exit-dimensions.md) ディメンションを使用）
* [!UICONTROL  ビーコンのマイナー ] （[ 入口 ](/help/components/dimensions/entry-dimensions.md) ディメンションと [ 出口 ](/help/components/dimensions/exit-dimensions.md) ディメンションを使用）
* [!UICONTROL  ビーコンの近接性 ] （[ 入口 ](/help/components/dimensions/entry-dimensions.md) ディメンションと [ 出口 ](/help/components/dimensions/exit-dimensions.md) ディメンションを使用）
* [!UICONTROL  ビーコン UUID] （[ 入口 ](/help/components/dimensions/entry-dimensions.md) ディメンションと [ 出口 ](/help/components/dimensions/exit-dimensions.md) ディメンションを使用）
* [!UICONTROL ロケーション（半径 10 km 以内）]
* [!UICONTROL ロケーション（半径 100 m 以内）]
* [!UICONTROL ロケーション（半径 1 m 以内）]
* [!UICONTROL 目標点名]
* [!UICONTROL 目標地点の中心までの距離]
* [!UICONTROL  目標点 ID]

## [!UICONTROL  ボイスとチャットボット ]

[!UICONTROL  音声およびチャットボット ] のディメンションと指標を使用すると、AlexaやGoogle ホームなどの音声アシスタントを測定できます。 また、自作のチャットボットを測定することもできます。 測定プロパティには以下が含まれます。

* **ライフサイクル**：任意のアプリに関するレポートの基盤レベル（起動数やプラットフォームタイプなど）。
* **会話**：会話に関連するインテント、応答、その他の指標およびディメンションを測定します。

[!UICONTROL  音声およびチャットボット ] を有効にすると、次の寸法を使用できます。

* [!UICONTROL  音声デバイス機能 ] （[ 入口 ](/help/components/dimensions/entry-dimensions.md) および [ 出口 ](/help/components/dimensions/exit-dimensions.md) ディメンションを使用）
* [!UICONTROL  音声認証 ]
* [!UICONTROL  音声エラーの種類 ]
* [!UICONTROL  音声インテント ]
* [!UICONTROL  音声アプリの応答 ]
* [!UICONTROL  音声言語 ]

以下の指標を使用できます。

* [!UICONTROL  音声終了セッション ]
* [!UICONTROL  音声エラー ]
* [!UICONTROL  発声 ]

## バックグラウンドヒットの従来のレポートおよび属性

レガシーレポートとは、アプリがバックグラウンドにあるときに生成されたヒットを、通常のフォアグラウンドのヒットとして扱うことを意味します。 これらはレポートに表示され、アトリビューションに影響を与えます。 通常、このレガシー設定は、レガシー実装との一貫性を維持するために使用します。

Adobeでは、バックグラウンドヒットが表示されないように、従来のレポートを無効にすることをお勧めします。 分析にバックグラウンドヒットを含める場合は、「[ 仮想レポートスイート ](/help/components/vrs/vrs-about.md)」設定 **[!UICONTROL バックグラウンドヒットを含める]** を有効にできます。
