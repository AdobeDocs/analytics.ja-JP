---
title: 地域
description: 訪問者の地域。
feature: Dimensions
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
TQID: https://experienceleague.adobe.com/Yjy-VGZ0alwfMR408QClnOEIB2z-rfgH5XCn9K0bE1A
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 73%
---
# 地域

「リージョン」 [ ディメンション ](overview.md)は、訪問者の地理的地域をレポートします。 国より小さく、市区町村より大きな地域です。 一部の国では、地域とは、州または都道府県を指します。 他の地域では、構成国、省、または大都市圏を指します。 このディメンションの使用は、インサイトの精度を[国](countries.md)よりも高くしたいが、[市区町村](cities.md)よりは低くしたい場合に役立ちます。

## このディメンションへのデータ入力

Adobeは、訪問者のIP アドレスからサーバーサイドでこのディメンションを取得し、内部ルックアップテーブルと照合します。 Adobeは[Digital Element](https://www.digitalelement.com/)と提携して、IP アドレスとリージョン間のルックアップを管理します。 設定する変数がありません。 このディメンションは、すべての実装で標準で利用できます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（訪問者のIP アドレスから取得） |
| **Web SDK / XDM フィールド** | なし（訪問者のIP アドレスから取得） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、地域とその地域の国が含まれます。 例えば、`"California (United States)"`、`"Tokyo (Japan)"`、`"Sao Paulo (Brazil)"` の値があります。

ディメンション項目には、ダイヤルアップインターネットサービスプロバイダーの `"AOL"` などが含まれる場合があります。 このサービスの購読者には、アカウント番号が確立された国に基づいてアクセスポイントが割り当てられます。 AOL ユーザーは、このアクセスポイントの IP アドレスを使用します。 このディメンションは IP アドレスに基づいているので、訪問者の実際の場所の代わりに、アクセスポイントの位置情報が使用されます。

## レポート場所と実際の場所の違い

このディメンションは IP アドレスに基づいているので、レポートされた場所と実際の場所の違いを示すシナリオもあります。

* **企業プロキシを表す IP アドレス**：これらの訪問者は、ユーザーの会社のネットワークを通るトラフィックとして表示される場合があります。ユーザーがリモートで作業している場合は、別の場所に配置することができます。
* **モバイル IP アドレス**：モバイル IP ターゲティングは、場所とネットワークに応じて様々なレベルで機能します。 いくつかの通信業者は、集中型または地域型の拠点を経由して IP トラフィックをバックホールしています。
* **Satellite ISP ユーザー**：これらのユーザーは通常、アップリンクの場所から派生しているように見えるので、特定の場所を識別するのは困難です。
* **軍事および政府の知的財産**：これはしばしば、人員が現在滞在しているベースやオフィスというより、世界中を旅行する人員がホーム場所を経由して入って来ていることを表します。
* プライバシー上の理由からIP アドレスを不明瞭にする&#x200B;**プロキシ**: Appleのプライベートリレーなどのサービスは、仲介者またはプロキシを介してデータをランダムに送信することで、真のIP アドレスを非表示にします。 このプロキシは、Adobeに転送する前に別のIP アドレスに置き換わります。
