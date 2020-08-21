---
title: 検索キーワード
description: 訪問者がサイトに到達する際に使用した検索キーワード。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 78%

---


# 検索キーワード

「検索キーワード」ディメンションは、訪問者がサイトに到達する際に使用する検索キーワードをレポートします。

>[!IMPORTANT]
>
>プライバシーに関する慣行が増えているため、ほとんどの検索エンジンは検索キーワードを渡さなくなりました。Hits where Adobe recognizes a search engine but is missing a keyword groups under the dimension item `"Keyword unavailable"`.

リファラーは、検索キーワードとして分類するために、次の両方と一致する必要があります。

* 参照ドメインは、アドビによって有効な[検索エンジン](search-engine.md)として認識されます。
* 参照 URL にキーワードクエリー文字列パラメーターが存在する。If the keyword query string exists but does not contain a value, it groups under the dimension item `"Keyword unavailable"`.

有料検索と自然検索を区別したい場合は、[有料検索検知](/help/admin/admin/paid-search-detection/paid-search-detection.md)が必要です。検索キーワードには、複数のディメンションを使用できます。

* **検索キーワード**：有料か自然かに関係なく、サイトに到達するために使用された検索キーワード。
* **検索キーワード — 有料**：サイトに到達するために使用された検索キーワードで、有料検索検知と一致するもの。
* **検索キーワード — 自然**：サイトに到達するために使用された検索キーワードで、有料検索検知と一致しなかったもの。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部の複数のルックアップテーブルを参照します。各値は、ヒットの[リファラー](referrer.md)（[内部 URL フィルター](/help/admin/admin/internal-url-filter-admin.md)に依存）に基づきます。リファラーディメンションと内部 URL フィルターが正しく設定されていることを確認します。

## Dimension項目

Dimension項目には、サイトの訪問に使用した検索キーワードが含まれます。 The `"Unspecified"` dimension item is all non-search traffic.
