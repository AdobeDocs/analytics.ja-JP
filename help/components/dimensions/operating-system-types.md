---
title: オペレーティングシステムの種類
description: オペレーティングシステムを表します。バージョンは関係ありません。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
TQID: https://experienceleague.adobe.com/onZ7Wt7A44gd42hqmjqYHL7OF6VtBke1NDgu1tsnMIg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 40%
---
# オペレーティングシステムの種類

「オペレーティングシステムの種類」の[&#x200B; ディメンション &#x200B;](overview.md)には、特定のバージョンに関係なく、訪問者が使用したOS全体が表示されます。 このディメンションを使用すると、最も一般的な特定のオペレーティングシステムやバージョンだけでなく、訪問者が通常どの OS プラットフォームを使用しているかも把握できます。

## このディメンションへのデータ入力

Adobeは、このディメンションを`User-Agent` HTTP ヘッダーから取得し、Adobeが[DeviceAtlas](https://deviceatlas.com/)と連携して保持する内部ルックアップテーブルと照合します。 設定する変数がありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（ユーザーエージェントから派生） |
| **Web SDK / XDM フィールド** | なし（ユーザーエージェントから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[&#x200B; データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Device Lookup]を有効にします。

## ディメンション項目

Dimensionの項目には、使用するオペレーティングシステムの種類が含まれます。 例として、`"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"`、`"Apple iOS"` があります。
