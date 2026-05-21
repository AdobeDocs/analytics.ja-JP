---
title: オペレーティングシステムの種類
description: オペレーティングシステムを表します。バージョンは関係ありません。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
TQID: https://experienceleague.adobe.com/onZ7Wt7A44gd42hqmjqYHL7OF6VtBke1NDgu1tsnMIg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 55%

---

# オペレーティングシステムの種類

「オペレーティングシステムの種類」の[&#x200B; ディメンション &#x200B;](overview.md)には、特定のバージョンに関係なく、訪問者が使用したOS全体が表示されます。 このディメンションは、特定のオペレーティングシステムとバージョンだけでなく、どのような一般的な OS プラットフォームを訪問者が使用するかを理解するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。 Adobeは[DeviceAtlas](https://deviceatlas.com/)と提携して、ユーザーエージェントとオペレーティングシステムの種類の間でルックアップを管理します。

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[&#x200B; データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Device Lookup]を有効にします。

## ディメンション項目

Dimensionの項目には、使用するオペレーティングシステムの種類が含まれます。 例として、`"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"`、`"Apple iOS"` があります。
