---
title: 米国 DMA
description: ヒットの指定された市場領域。
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
TQID: https://experienceleague.adobe.com/ijUlnHJ7gP4Jq1g0SzaUVHWbiMki1rgEMd1Pz4sttmU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 55%
---
# 米国 DMA

「米国DMA」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者の指定された市場領域（DMA）を報告します。 これは、[Nielsen 社](https://www.nielsen.com/dma-regions/)がまとめたメディア市場に基づいています。

## このディメンションへのデータ入力

Adobeは、訪問者のIP アドレスからサーバーサイドでこのディメンションを取得し、内部ルックアップテーブルと照合します。 AdobeはNielsenと提携して、IP アドレスとDMA間のルックアップを管理します。 設定する変数がありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（訪問者のIP アドレスから取得） |
| **Web SDK / XDM フィールド** | なし（訪問者のIP アドレスから取得） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[&#x200B; データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Geo Lookup]を有効にします。

## ディメンション項目

Dimensionの項目には、訪問者のDMA コードとDMA コードが含まれます。 3 桁のコードは郵便番号ではなく、Nielsen の DMA コードです。 例えば、`"Dallas-Ft. Worth (623)"`、`"New York (501)"`、`"Los Angeles (803)"` の値があります。 ディメンション値 `"No Metro (0)"` には、米国以外のすべての国際トラフィックが含まれます。

## レポート場所と実際の場所の違い

このディメンションは IP アドレスに基づいているので、レポートされた場所と実際の場所の違いを示すシナリオもあります。

* **企業プロキシを表す IP アドレス**：これらの訪問者は、ユーザーの会社のネットワークを通るトラフィックとして表示される場合があります。ユーザーがリモートで作業している場合は、別の場所に配置することができます。
* **モバイル IP アドレス**：モバイル IP ターゲティングは、場所とネットワークに応じて様々なレベルで機能します。 一部の通信事業者は、IP トラフィックを一元化されたポイントまたは地域のポイントからバックホールします。
* **Satellite ISP ユーザー**：これらのユーザーは通常、アップリンクの場所から派生しているように見えるので、特定の場所を識別するのは困難です。
* **軍事および政府の知的財産**：これはしばしば、人員が現在滞在しているベースやオフィスというより、世界中を旅行する人員がホーム場所を経由して入って来ていることを表します。
* プライバシー上の理由からIP アドレスを不明瞭にする&#x200B;**プロキシ**: Appleのプライベートリレーなどのサービスは、仲介者またはプロキシを介してデータをランダムに送信することで、真のIP アドレスを非表示にします。 このプロキシは、Adobeに転送する前に別のIP アドレスに置き換わります。
