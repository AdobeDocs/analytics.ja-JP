---
title: 検索エンジン
description: 訪問者がサイトに到達するのに使用した検索エンジン。
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 69%
---
# 検索エンジン

「検索エンジン」 [ ディメンション ](overview.md)は、訪問者がサイトに到達するために使用する検索エンジンを報告します。 リファラーは、検索エンジンとして分類するために、次の両方と一致する必要があります。

* 参照ドメインは、アドビによって有効な検索エンジンとして認識されます。
* 参照 URL にキーワードクエリ文字列パラメーターが存在する。 クエリ文字列パラメーターは空白にすることができます（プライバシー保護のため、いくつかの検索エンジンではこのパラメーターが空白になる場合があります）。

有料検索と自然検索を区別したい場合は、[有料検索検知](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)が必要です。 検索エンジンには、複数のディメンションを使用できます。

* **検索エンジン**：有料か自然かに関係なく、サイトに到達するために使用する検索エンジン。
* **検索エンジン — 有料**：サイトに到達するのに使用した検索エンジンで、有料検索検知と一致するもの。
* **検索エンジン — 自然**：サイトの訪問に使用した検索エンジンで、有料検索検知と一致しなかった。

## このディメンションへのデータ入力

Adobeは、各ヒットの[ リファラー](referrer.md)からこのディメンションを取得し、Adobeの内部にある複数のルックアップテーブルと照合します。 設定する変数がありません。 各値はリファラーに依存するため、リファラーディメンションと[内部URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)が正しく設定されていることを確認してください。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（リファラーから派生） |
| **Web SDK / XDM フィールド** | なし（リファラーから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、サイトに到達するために使用される検索エンジンが含まれます。 例えば、`"Google"`、`"Microsoft Bing"`、`"DuckDuckGo"` などの値があります。 `"Unspecified"` ディメンション項目は、すべて検索以外のトラフィックです。
