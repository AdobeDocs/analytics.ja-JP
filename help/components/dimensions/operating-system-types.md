---
title: オペレーティングシステムの種類
description: オペレーティングシステムを表します。バージョンは関係ありません。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 55%

---

# オペレーティングシステムの種類

「オペレーティングシステムの種類」 [ディメンション](overview.md) は、特定のバージョンに関係なく、訪問者が使用した包括的な OS を表示します。 このディメンションは、特定のオペレーティングシステムとバージョンだけでなく、どのような一般的な OS プラットフォームを訪問者が使用するかを理解するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。Adobeパートナーと [DeviceAtlas](https://deviceatlas.com/) ユーザーエージェントとオペレーティングシステムの種類の間の検索を維持する。

* AppMeasurement実装の場合、このディメンションは初期設定の状態で動作します。
* Web SDK 実装の場合、を有効にします。 [!UICONTROL デバイス参照] when [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja).

## ディメンション項目

Dimension項目には、使用するオペレーティングシステムの種類が含まれます。 例として、`"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"`、`"Apple iOS"` があります。
