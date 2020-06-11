---
title: オペレーティングシステムの種類
description: バージョンに関係なく、オペレーティングシステム。
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# オペレーティングシステムの種類

「オペレーティングシステムの種類」ディメンションは、特定のバージョンに関係なく、訪問者が使用したオーバーチOSを示します。 このディメンションは、特定のオペレーティングシステムとバージョンだけでなく、どのような一般的なOSプラットフォーム訪問者が使用するかを理解するのに役立ちます。

## このディメンションにデータを入力する

このディメンションは、Adobe内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `User-Agent` HTTPヘッダーに基づきます。 （Adobe Experience Platform Launch経由などの）AppMeasurementライブラリを使用する場合、このディメンションは初期設定の状態で動作します。

## 分析コード値

ディメンション値には、使用するオペレーティングシステムの種類が含まれます。 Examples include `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`, and `"Apple iOS"`.
