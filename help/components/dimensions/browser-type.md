---
title: ブラウザータイプ
description: ブラウザーを作成した組織。
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 69%

---

# ブラウザータイプ

「ブラウザーのタイプ」 [ディメンション](overview.md) 訪問者が使用するブラウザーを作成した組織が一覧表示されます。 このディメンションは、訪問者が使用するブラウザーを包括的に確認する場合に役立ちます。「ブラウザー」ディメンションに対する値を提供するのは、同じブラウザーの異なるバージョンが別々のディメンション項目としてリストされない点です。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。Adobeパートナーと [DeviceAtlas](https://deviceatlas.com/) ユーザーエージェントとブラウザー間の検索を維持する。

* AppMeasurement実装の場合、このディメンションは初期設定の状態で動作します。
* Web SDK 実装の場合、を有効にします。 [!UICONTROL デバイス参照] when [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja).

## ディメンション項目

ディメンション項目には、ブラウザーを作成する組織が含まれます。一般的なディメンション項目には、`"Google"`（[!DNL Chrome] の作成者）、`"Apple"`（[!DNL Safari] の作成者）、`"Microsoft"`（[!DNL Edge] の作成者）、`"Mozilla"`（[!DNL Firefox] の作成者）があります。
