---
title: IP アドレス
description: 各ヒットが送信されたIP アドレス（Data Warehouseで使用可能）。
feature: Dimensions
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
source-wordcount: '153'
ht-degree: 16%
---
# IP アドレス

「IP アドレス」 [&#x200B; ディメンション &#x200B;](overview.md)には、各ヒットが送信されたIP アドレスが一覧表示されます。

>[!IMPORTANT]
>
>このディメンションは、Data Warehouse でのみ使用できます。

## このディメンションへのデータ入力

AppMeasurementは、各イメージリクエストのHTTP ヘッダーからIP アドレスを自動的に収集します。 データフィードの`ip`列に対応します。 詳しくは、[&#x200B; データ列リファレンス &#x200B;](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)を参照してください。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（HTTP リクエストから） |
| **Web SDK / XDM フィールド** | なし（HTTP リクエストから） |
| **クエリパラメーター** | なし（HTTP リクエストから） |
| **XML タグ** | [`<ipAddress>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

レポートスイートの[一般アカウント設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)で[!UICONTROL IP難読化]が有効になっている場合、Data Warehouseを含むAnalyticsのあらゆる場所でIP アドレスが難読化または削除されます。

## ディメンション項目

Dimensionの項目には、ヒットが送信されたIP アドレスが含まれます。
