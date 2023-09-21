---
title: オペレーティングシステムの種類
description: オペレーティングシステムを表します。バージョンは関係ありません。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 85%

---

# オペレーティングシステムの種類

「オペレーティングシステムの種類」 [ディメンション](overview.md) は、特定のバージョンに関係なく、訪問者が使用した包括的な OS を示します。 このディメンションは、特定のオペレーティングシステムとバージョンだけでなく、どのような一般的な OS プラットフォームを訪問者が使用するかを理解するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、使用するオペレーティングシステムの種類が含まれます。例として、`"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"`、`"Apple iOS"` があります。
