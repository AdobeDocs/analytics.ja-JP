---
title: オペレーティングシステム
description: 訪問者のオペレーティングシステム。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 45%

---

# オペレーティングシステム

「オペレーティングシステム」 [ディメンション](overview.md) 訪問者が使用したオペレーティングシステムとバージョンを表示します。 Web プロパティに OS 固有の機能がある場合、このディメンションは、最も一般的なオペレーティングシステムを示します。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。Adobeパートナーと [DeviceAtlas](https://deviceatlas.com/) ユーザーエージェントとオペレーティングシステム間の検索を維持する。

* AppMeasurement実装の場合、このディメンションは初期設定の状態で動作します。
* Web SDK 実装の場合、を有効にします。 [!UICONTROL デバイス参照] when [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja).

## ディメンション項目

ディメンション項目には、訪問者が使用するオペレーティングシステムが含まれます。例として、`"Windows 10"`、`"OS X 10.15.7"`、および `"Android 9"` があります。

## 正確な OS バージョンの追跡

業界がクライアントのヒントに近づくにつれ、一部のオペレーティングシステムのバージョンが統合される可能性があります。 例えば、高エントロピーのクライアントヒントを収集しない場合、「Windows 10」と「Windows 11」の両方を「Windows 10」の下にグループ化できます。 詳しくは、 [クライアントヒント](/help/technotes/client-hints.md) （技術注記ガイド）を参照してください。
