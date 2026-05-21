---
title: オペレーティングシステム
description: 訪問者のオペレーティングシステム。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
TQID: https://experienceleague.adobe.com/WM6GQ-AhLmtudRWXF6lOez6DaVxMBU3rSaEb2UdsXdc
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
source-wordcount: 178
ht-degree: 45%

---

# オペレーティングシステム

「オペレーティングシステム」 [&#x200B; ディメンション &#x200B;](overview.md)には、訪問者が使用したオペレーティングシステムとバージョンが表示されます。 Web プロパティに OS 固有の機能がある場合、このディメンションは、最も一般的なオペレーティングシステムを示します。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。 ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。 Adobeは[DeviceAtlas](https://deviceatlas.com/)と提携して、ユーザーエージェントとオペレーティングシステム間のルックアップを維持します。

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[&#x200B; データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Device Lookup]を有効にします。

## ディメンション項目

ディメンション項目には、訪問者が使用するオペレーティングシステムが含まれます。 例として、`"Windows 10"`、`"OS X 10.15.7"`、および `"Android 9"` があります。

## 正確なOS バージョンのトラッキング

業界がクライアントヒントに移行するにつれ、一部のオペレーティングシステムのバージョンが競合する可能性があります。 例えば、「Windows 10」と「Windows 11」は、高エントロピーのクライアントヒントを収集しない場合、「Windows 10」の下にグループ化できます。 詳しくは、『 Technotes ガイド』の「[&#x200B; クライアントヒント &#x200B;](/help/technotes/client-hints.md)」を参照してください。
