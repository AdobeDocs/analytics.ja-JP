---
title: オペレーティングシステム
description: 訪問者のオペレーティングシステム。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 42%

---

# オペレーティングシステム

「オペレーティングシステム」 [&#x200B; ディメンション &#x200B;](overview.md) は、訪問者が使用したオペレーティングシステムとバージョンを示します。 Web プロパティに OS 固有の機能がある場合、このディメンションは、最も一般的なオペレーティングシステムを示します。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。Adobeは [DeviceAtlas](https://deviceatlas.com/) と提携して、ユーザーエージェントとオペレーティングシステム間のルックアップを管理しています。

* AppMeasurement実装の場合、このディメンションは初期設定の状態で動作します。
* Web SDK実装の場合、「データストリームの設定 [!UICONTROL &#x200B; 時に &#x200B;] デバイス検索 [&#x200B; を有効に &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja) ます。

## ディメンション項目

ディメンション項目には、訪問者が使用するオペレーティングシステムが含まれます。例として、`"Windows 10"`、`"OS X 10.15.7"`、および `"Android 9"` があります。

## 正確な OS バージョンの追跡

業界がクライアントヒントに向かうにつれて、一部のオペレーティングシステムバージョンは競合する可能性があります。 例えば、高エントロピーのクライアントヒントを収集しない場合、「Windows 10」と「Windows 11」は、両方とも「Windows 10」の下にグループ化できます。 詳しくは、テクニカルノートガイドの [Client hints](/help/technotes/client-hints.md) を参照してください。
