---
description: リアルタイムページ分析（ライブモード）により、分単位の精度でリアルタイムに結果を取得できます。
title: リアルタイム（ライブ）ページ分析
topic: Activity map
uuid: a3faa9bd-73d8-48b3-be2b-f818ed7456fb
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# リアルタイム（ライブ）ページ分析

リアルタイムページ分析（ライブモード）により、分単位の精度でリアルタイムに結果を取得できます。

Activity Map では、分析データが 1～15 分刻みで表示され、選択したページのマイクロトレンドに基づいてリンクの人気度を監視できます。これは、出版業者が物語への関心の上昇、下降を追跡して対応し、リアルタイムのトラフィックフローを監視する場合に特に重要です。

サイトコンテンツ所有者としての役割の 1 つに、コンテンツのプロモーションや削除のタイミングを理解し、適切なユーザーエクスペリエンスを維持することがあります。リアルタイムデータはこの責務に不可欠です。現時点でどんなリンクやコンテンツがトレンドかを理解できれば、迅速に断固として行動し、自身のブランドに顧客をつなぎとめることができます。

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## A4T 設定によるデータ遅延 {#section_806CE36354FC4C539A0DED9266A5C704}

Adobe Target で A4T 統合を有効にすると、Adobe Analytics で 5～10 分の待ち時間が追加で発生します。この追加の待ち時間は、Analytics と Target からのデータを同じヒットに格納することによって、ページおよびサイトセクションによってテストを分類できるようにするためのものです。

この追加の待ち時間は、ライブストリームやリアルタイムレポートなどのすべての Adobe Analytics サービスおよびツールで発生します。追加の待ち時間が発生する対象となるヒットは次のとおりです。

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標の現在のデータ、ファイナライズされたデータ、データフィードでは、すべてのヒットが追加で 5 ～ 7 分遅延します。

この統合を完全に実装していなくても、[ID サービス](https://marketing.adobe.com/resources/help/ja_JP/mcvid/)を導入すると追加の待ち時間が発生することに注意してください。
