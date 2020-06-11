---
title: ブラウザーのタイプ
description: ブラウザーを作成した組織。
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 3%

---


# ブラウザーのタイプ

「ブラウザータイプ」ディメンションは、訪問者が使用するブラウザーを作成したリスト組織を分析します。 このディメンションは、訪問者が使用するオーバーカッチブラウザーを確認する場合に役立ちます。 「ブラウザー」ディメンションに対する値を提供するのは、同じブラウザーの異なるバージョンが別々のディメンション値としてリストされない点です。

## このディメンションにデータを入力する

このディメンションは、Adobe内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `User-Agent` HTTPヘッダーに基づきます。 （Adobe Experience Platform Launch経由などの）AppMeasurementライブラリを使用する場合、このディメンションは初期設定の状態で動作します。

## 分析コード値

ディメンション値には、ブラウザーを作成する組織が含まれます。 一般的なディメンション値には、（作成者）、（作成者）、 `"Google"` (作成者 [!DNL Chrome])、 `"Apple"` （作成者）、 [!DNL Safari](作成者 `"Microsoft"`[!DNL Edge]`"Mozilla"`[!DNL Firefox])、（作成者の作成者）があります。
