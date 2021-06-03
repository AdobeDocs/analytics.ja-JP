---
description: リアルタイムページ分析（ライブモード）により、分単位の精度でリアルタイムに結果を取得できます。
title: リアルタイム（ライブ）ページ分析
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 29ccd89e-d82b-41d4-a940-addc6656b5ec
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 67%

---

# リアルタイムページ分析（ライブモード）

リアルタイムページ分析（ライブモード）により、分単位の精度でリアルタイムに結果を取得できます。

Activity Mapに分析データが1分～ 15分刻みで表示され、選択したページのマイクロトレンドに基づいてリンクの人気度を監視できるようになりました。 これは、出版業者が物語への関心の上昇、下降を追跡して対応し、リアルタイムのトラフィックフローを監視する場合に特に重要です。

サイトコンテンツ所有者としての役割の 1 つに、コンテンツのプロモーションや削除のタイミングを理解し、適切なユーザーエクスペリエンスを維持することがあります。リアルタイムデータはこの責務に不可欠です。現時点でどんなリンクやコンテンツがトレンドかを理解できれば、迅速に断固として行動し、自身のブランドに顧客をつなぎとめることができます。

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

ライブモードでどの要素がほとんどクリックされているかを確認する場合は、次の手順に従います。

1. 分析するツールバーの&#x200B;**[!UICONTROL ライブモード]**&#x200B;トレンドライン上の期間を選択します。
1. ツールバーの「目」アイコンをクリックして、リンクレポートテーブルにアクセスします。
1. 「リンク」でテーブルを並べ替えます。

## A4T 設定によるデータ遅延

Adobe Targetで[A4T統合](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html)を有効にすると、Adobe Analyticsで5 ～ 10分の待ち時間が追加で発生します。 この追加の待ち時間は、Analytics と Target からのデータを同じヒットに格納することによって、ページおよびサイトセクションによってテストを分類できるようにするためのものです。

この追加の待ち時間は、ライブストリームやリアルタイムレポートなどのすべての Adobe Analytics サービスおよびツールで発生します。追加の待ち時間が発生する対象となるヒットは次のとおりです。

* ライブストリーム、リアルタイムのレポートと API リクエスト、トラフィック変数の現在のデータでは、追加のデータ ID が設定されたヒットのみが遅延します。
* コンバージョン指標の現在のデータ、ファイナライズされたデータ、データフィードでは、すべてのヒットが追加で 5 ～ 7 分遅延します。

この統合を完全に実装していなくても、[ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html)を導入すると追加の待ち時間が発生することに注意してください。

詳細[ここ](/help/analyze/activity-map/activitymap-standard-live.md)。
