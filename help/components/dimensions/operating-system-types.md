---
title: オペレーティングシステムの種類
description: バージョンに関係なく、オペレーティングシステム。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# オペレーティングシステムの種類

「オペレーティングシステムの種類」ディメンションは、特定のバージョンに関係なく、訪問者が使用したオーバーチOSを示します。 このディメンションは、特定のオペレーティングシステムとバージョンだけでなく、どのような一般的なOSプラットフォーム訪問者が使用するかを理解するのに役立ちます。

## このディメンションにデータを入力する

このディメンションは、Adobe内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `User-Agent` HTTPヘッダーに基づきます。 (Adobe Experience Platform起動を介したなどの)AppMeasurementライブラリを使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、使用するオペレーティングシステムの種類が含まれます。 Examples include `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`, and `"Apple iOS"`.
