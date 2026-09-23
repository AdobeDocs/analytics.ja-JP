---
title: 接続タイプ
description: 訪問者がインターネットに接続する方法。
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
TQID: https://experienceleague.adobe.com/5kdDrW5vGzc4EKpLOF4VWzXish439t-aGp6q-XcK3Fs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 76%
---
# 接続タイプ

「接続タイプ」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者がインターネットに接続した方法を示します。 このディメンションは、訪問者がサイトを閲覧する際にどのようにインターネットに接続するかを判断するのに役立ちます。 これを使用して、訪問者の接続速度に基づいてサイトのコンテンツを最適化できます。

## このディメンションへのデータ入力

このディメンションは、設定した変数ではなく、収集されたデータとAdobe サーバーサイドロジックの組み合わせによって決定されます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし |
| **Web SDK / XDM フィールド** | なし |
| **クエリパラメーター** | [`ct`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<connectionType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

アドビは、値を決定するために次のルールを使用します。

1. `ct` クエリ文字列が `"modem"` に等しい場合は、ディメンション項目を `"Modem"` に設定します。 AppMeasurement は、サポートされていない Internet Explorer ブラウザーでのみこのデータを収集するため、このディメンション項目は一般的ではありません。
1. ヒットの IP アドレスを確認し、アドビ内部のルックアップテーブルを参照します。 IP アドレスが携帯電話会社からのものである場合は、ディメンション項目を `"Mobile Carrier"` に設定します。
1. `ct` クエリ文字列が `"lan"` に等しい場合は、ディメンション項目を `"LAN/Wifi"` に設定します。
1. ヒットが[データソース &#x200B;](/help/import/data-sources/overview.md)から発生した場合、または特別なタイプのヒットと見なされる場合は、ディメンション項目を `"Not specified"` に設定します。
1. 上記の規則がいずれも満たされない場合、デフォルト値は `"LAN/Wifi"` です。

## ディメンション項目

ディメンション項目には、`LAN/Wifi`、`Mobile Carrier`、`Modem`、`Not Specified` があります。

* **`LAN/Wifi`**：訪問者が固定回線または Wi-Fi ホットスポットを通じてインターネットに接続した。
* **`Mobile Carrier`**：訪問者が携帯電話会社を通じてインターネットに接続した。
* **`Modem`**：訪問者がサポートされていない Internet Explorer ブラウザーのモデムを通じてインターネットに接続した。
* **`Not Specified`**：ヒットに接続タイプがありませんでした。
