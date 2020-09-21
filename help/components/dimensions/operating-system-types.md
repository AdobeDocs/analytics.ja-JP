---
title: オペレーティングシステムの種類
description: オペレーティングシステムを表します。バージョンは関係ありません。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '112'
ht-degree: 100%

---


# オペレーティングシステムの種類

「オペレーティングシステムの種類」ディメンションは、特定のバージョンに関係なく、訪問者が使用した OS を包括的に示します。このディメンションは、特定のオペレーティングシステムとバージョンだけでなく、どのような一般的な OS プラットフォームを訪問者が使用するかを理解するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、使用するオペレーティングシステムの種類が含まれます。例として、`"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"`、`"Apple iOS"` があります。
