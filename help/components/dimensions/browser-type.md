---
title: ブラウザータイプ
description: ブラウザーを作成した組織。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '133'
ht-degree: 100%

---


# ブラウザータイプ

「ブラウザータイプ」ディメンションは、訪問者が使用するブラウザーを作成したリスト組織を分析します。このディメンションは、訪問者が使用するブラウザーを包括的に確認する場合に役立ちます。「ブラウザー」ディメンションに対する値を提供するのは、同じブラウザーの異なるバージョンが別々のディメンション項目としてリストされない点です。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、ブラウザーを作成する組織が含まれます。一般的なディメンション項目には、`"Google"`（[!DNL Chrome] の作成者）、`"Apple"`（[!DNL Safari] の作成者）、`"Microsoft"`（[!DNL Edge] の作成者）、`"Mozilla"`（[!DNL Firefox] の作成者）があります。
