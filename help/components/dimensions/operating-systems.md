---
title: オペレーティングシステム
description: 訪問者のオペレーティングシステム。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '105'
ht-degree: 100%

---

# オペレーティングシステム

「オペレーティングシステム」ディメンションは、訪問者が使用していたオペレーティングシステムとバージョンを示します。Web プロパティに OS 固有の機能がある場合、このディメンションは、最も一般的なオペレーティングシステムを示します。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、訪問者が使用するオペレーティングシステムが含まれます。例として、`"Windows 10"`、`"OS X 10.15"`、および `"Android 9"` があります。
