---
title: ブラウザータイプ
description: ブラウザーを作成した組織。
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
TQID: https://experienceleague.adobe.com/Qb4g-5RXrK42ui4xG86YEv3ozVqmqHrn9Bj5zqXmzPU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 69%

---

# ブラウザータイプ

「ブラウザータイプ」 [ ディメンション ](overview.md)には、訪問者が使用するブラウザーを作成した組織が一覧表示されます。 このディメンションは、訪問者が使用するブラウザーを包括的に確認する場合に役立ちます。 「ブラウザー」ディメンションに対する値を提供するのは、同じブラウザーの異なるバージョンが別々のディメンション項目としてリストされない点です。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。 Adobeは[DeviceAtlas](https://deviceatlas.com/)と提携して、ユーザーエージェントとブラウザー間のルックアップを管理します。

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[ データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Device Lookup]を有効にします。

## ディメンション項目

ディメンション項目には、ブラウザーを作成する組織が含まれます。 一般的なディメンション項目には、`"Google"`（[!DNL Chrome] の作成者）、`"Apple"`（[!DNL Safari] の作成者）、`"Microsoft"`（[!DNL Edge] の作成者）、`"Mozilla"`（[!DNL Firefox] の作成者）があります。
