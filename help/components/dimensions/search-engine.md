---
title: 検索エンジン
description: 訪問者がサイトに到達するのに使用した検索エンジン。
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 93%

---

# 検索エンジン

「検索エンジン」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者がサイトに到達するために使用する検索エンジンを報告します。 リファラーは、検索エンジンとして分類するために、次の両方と一致する必要があります。

* 参照ドメインは、アドビによって有効な検索エンジンとして認識されます。
* 参照 URL にキーワードクエリ文字列パラメーターが存在する。 クエリ文字列パラメーターは空白にすることができます（プライバシーに関する慣行が原因で、複数の検索エンジンで使用される場合と同様です）。

有料検索と自然検索を区別したい場合は、[有料検索検知](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)が必要です。 検索エンジンには、複数のディメンションを使用できます。

* **検索エンジン**：有料か自然かに関係なく、サイトに到達するために使用する検索エンジン。
* **検索エンジン — 有料**：サイトに到達するのに使用した検索エンジンで、有料検索検知と一致するもの。
* **検索エンジン — 自然**：サイトの訪問に使用した検索エンジンで、有料検索検知と一致しなかった。

## このディメンションへのデータ入力

このディメンションは、アドビ内部の複数のルックアップテーブルを参照します。 各値は、ヒットの[リファラー](referrer.md)（[内部 URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)に依存）に基づきます。 リファラーディメンションと内部 URL フィルターが正しく設定されていることを確認します。

## ディメンション項目

ディメンション項目には、サイトに到達するために使用される検索エンジンが含まれます。 例えば、`"Google"`、`"Microsoft Bing"`、`"DuckDuckGo"` などの値があります。 `"Unspecified"` ディメンション項目は、すべて検索以外のトラフィックです。
