---
title: cookie サポート
description: ブラウザーが cookie をサポートするかどうかを判別します。
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 38%
---
# cookie サポート

&#39;Cookie サポート&#39; [ ディメンション ](overview.md)は、ブラウザーが特定のヒットに対するCookieをサポートしているかどうかを報告します。 これは、cookie をサポートするブラウザーを使用する訪問者と、cookie を意図的に無効にしている訪問者の割合を判断するのに役立ちます。

## このディメンションへのデータ入力

Cookieのサポートは自動的に収集されます。クライアントサイド：AppMeasurementは、`s_cc`という名前のCookieを設定しようとし、そのCookieが存在するかどうかをレポートします。ブラウザーがCookieをサポートし、有効にしている場合は`Y`、Cookieが無効になっている場合は`N`。 AppMeasurementまたはWeb SDK（タグ）の実装では、設定することのできない機能です。 AppMeasurementまたはWeb SDK以外（API経由など）でデータを収集する場合は、各ヒットで`Y`または`N`を送信します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（自動収集） |
| **Web SDK / XDM フィールド** | なし（自動収集） |
| **クエリパラメーター** | [`k`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<cookiesEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 1 バイト |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目の値には、`Enabled`、`Disabled`、`Unknown` が含まれます。

* **`Enabled`**：ブラウザーは cookie をサポートし、cookie を有効にしています。
* **`Disabled`**：ブラウザーが cookie をサポートしていないか、訪問者が cookie を無効にしています。
* **`Unknown`**：AppMeasurement は cookie サポートを判断できませんでした。 イメージリクエストに `k` クエリ文字列が存在しませんでした。
