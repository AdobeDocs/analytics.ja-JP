---
title: Java 有効
description: Java がブラウザーで有効になっているかどうかを特定します。
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
source-wordcount: '249'
ht-degree: 51%
---
# Java 有効

「Javaが有効になりました」 [ ディメンション ](overview.md)は、当時のブラウザーでJavaが有効になっているかどうかを判断します。 Java ベースの機能をサイトに導入し、既に Java が有効になっている訪問者の数を知りたい場合に便利です。 Java を無効にしているユーザーには、Java を有効にする方法に関する代替情報や指示を提供できます。

## このディメンションへのデータ入力

Javaが有効になっている場合は、クライアント側で自動的に収集されます。AppMeasurementは、ブラウザーでJavaが有効になっているかどうかを検出し、「Y」または「N」とレポートします。 AppMeasurementまたはWeb SDK（タグ）の実装では、設定することのできない機能です。 AppMeasurementまたはWeb SDK以外（API経由など）でデータを収集する場合は、「Y」または「N」を送信して、このディメンションを使用します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（自動収集） |
| **Web SDK / XDM フィールド** | なし（自動収集） |
| **クエリパラメーター** | [`v`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<javaEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 1 バイト |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、「有効」、「無効」、「不明」があります。

* **有効**：Java がブラウザーで有効になっている。 `v` クエリ文字列には値「Y」が含まれていました。
* **無効**：Java がブラウザーで無効になっているか、無効になっていなくても Java がサポートされていません。 `v` クエリ文字列には値「N」が含まれていました。
* **不明**：AppMeasurement は Java サポートを特定できませんでした。 イメージリクエストに `v` クエリ文字列が存在しませんでした。
