---
title: 検索キーワード
description: 訪問者がサイトに到達する際に使用した検索キーワード。
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
TQID: https://experienceleague.adobe.com/4naavrC42ddsxGFJfkOJ0wzHLTa7tdMeI9nKDgVWrBY
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
source-wordcount: 251
ht-degree: 94%

---

# 検索キーワード

「検索キーワード」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者がサイトに到達するために使用する検索キーワードをレポートします。

>[!IMPORTANT]
>
>プライバシーに関する慣行が増えているため、ほとんどの検索エンジンは検索キーワードを渡さなくなりました。 アドビが検索エンジンを認識しても、ディメンション項目 `"Keyword unavailable"` の下にキーワードグループがないヒット。

リファラーは、検索キーワードとして分類するために、次の両方と一致する必要があります。

* 参照ドメインは、アドビによって有効な[検索エンジン](search-engine.md)として認識されます。
* 参照 URL にキーワードクエリ文字列パラメーターが存在する。 キーワードクエリ文字列が存在し、値が含まれない場合、そのキーワード文字列はディメンション項目 `"Keyword unavailable"` の下にグループ化されます。

有料検索と自然検索を区別したい場合は、[有料検索検知](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)が必要です。 検索キーワードには、複数のディメンションを使用できます。

* **検索キーワード**：有料か自然かに関係なく、サイトに到達するために使用された検索キーワード。
* **検索キーワード — 有料**：サイトに到達するために使用された検索キーワードで、有料検索検知と一致するもの。
* **検索キーワード — 自然**：サイトに到達するために使用された検索キーワードで、有料検索検知と一致しなかったもの。

## このディメンションへのデータ入力

このディメンションは、アドビ内部の複数のルックアップテーブルを参照します。 各値は、ヒットの[リファラー](referrer.md)（[内部 URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)に依存）に基づきます。 リファラーディメンションと内部 URL フィルターが正しく設定されていることを確認します。

## ディメンション項目

ディメンション項目には、サイトに到達するために使用される検索キーワードが含まれます。 `"Unspecified"` ディメンション項目は、すべて検索以外のトラフィックです。
